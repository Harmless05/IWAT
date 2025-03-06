# IWAT - Intune Win32 App Management Tool

IWAT is a PowerShell-based utility designed to simplify the process of packaging, managing, and uploading Win32 applications for Microsoft Intune deployment.

## Features

- Package .exe and .msi files into .intunewin format for Intune deployment
- View and manage existing packaged applications
- Configurable paths for IntuneWinAppUtil and output directories
- User-friendly menu interface for easy navigation
- Configuration persistence between sessions
- Integration with Microsoft's IntuneWinAppUtil

## Requirements

- Windows 10/11
- PowerShell 5.1 or later
- [Microsoft Win32 Content Prep Tool](https://github.com/microsoft/Microsoft-Win32-Content-Prep-Tool)
- Administrative privileges (recommended)

## Installation

1. Clone this repository or download the script: `git clone https://github.com/yourusername/IWAT.git`
2. Run the script in PowerShell: `powershell -ExecutionPolicy Bypass -File Intune-win32-app-v2.ps1`
3. On first run, the script will prompt you to select the location of IntuneWinAppUtil.exe

## Running the Script

By default, Windows restricts running unsigned PowerShell scripts. You have several options to run the script:

### Option 1: Bypass execution policy for a single script
```powershell
powershell -ExecutionPolicy Bypass -File Intune-win32-app-v2.ps1
```

### Option 2: Temporarily change execution policy in current session
```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\Intune-win32-app-v2.ps1
```

### Option 3: Unblock the script file (recommended for trusted scripts)
```powershell
Unblock-File -Path .\Intune-win32-app-v2.ps1
.\Intune-win32-app-v2.ps1
```
> [!IMPORTANT]
> **Note**: Always review scripts before running them with bypassed execution policies to ensure they're from trusted sources.

## Usage

### Main Menu

1. **Package application for Intune** - Convert .exe/.msi files to .intunewin format
2. **View packaged applications** - List all previously packaged applications
3. **Upload application to Intune** - (Future feature) Upload packages to Intune
4. **Settings** - Configure paths and options
0. **Exit** - Close the application

### Packaging Applications

1. Select option 1 from the main menu
2. Browse and select the .exe or .msi file you want to package
3. If IntuneWinAppUtil path is not configured, you'll be prompted to select it
4. The tool will create an .intunewin package in the configured output directory

### Settings

1. **Change IntuneWinAppUtil path** - Update the path to IntuneWinAppUtil.exe
2. **Change output directory** - Select where packaged applications will be stored
3. **View current configuration** - Display all current settings
4. **Reset configuration** - Restore default settings

## Configuration

The default configuration is located at: `%USERPROFILE%\Documents\IntuneWin32AppTool.config.json`

This includes:
- Path to IntuneWinAppUtil.exe
- Output directory for packaged applications

## License

This project is licensed under the Mozilla Public License 2.0 - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Acknowledgments

- Microsoft for creating the [Win32 Content Prep Tool](https://github.com/microsoft/Microsoft-Win32-Content-Prep-Tool)
