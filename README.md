# FortiSASE Made Easy

A cross-platform desktop application for bulk importing hosts and groups into FortiSASE.

## Features

- **Auto-Update System**: Automatic update notifications with secure signature verification (v1.0.0+)
- **Excel to CSV Conversion**: Convert Excel host lists to FortiSASE-compatible CSV format with automatic hostname sanitization
- **Bulk Import**: Import hundreds or thousands of hosts via FortiSASE REST API with real-time progress tracking
- **Group Management**: Flexible group update modes (Ask, Merge, Overwrite) for safe updates
- **Undo/Rollback**: Automatically rollback failed imports with one click
- **Secure Credential Storage**: Windows DPAPI encryption for stored API credentials
- **User-Friendly Interface**: Modern cross-platform UI built with .NET and Avalonia

## Download

**Latest Release:** [v1.0.0](https://github.com/gwilliamspro/FortiSASE-Made-Easy-Releases/releases/latest) - **First Official Stable Release!**

### System Requirements

- **Windows:** Windows 10/11 (64-bit) ✅
- **macOS:** macOS 11+ (Intel or Apple Silicon) - *Requires native Mac build (coming soon)*
- **Linux:** Ubuntu 20.04+ or equivalent - *Coming soon*

### Installation

#### Windows
1. Download `FortiSASE-Made-Easy-v1.0.0-win-x64.zip` from the [latest release](https://github.com/gwilliamspro/FortiSASE-Made-Easy-Releases/releases/latest)
2. Extract the zip file
3. Run `FortiSASE.App.exe`
4. No installation required - runs standalone
5. **Auto-updates enabled** - Future versions will be detected automatically


## Quick Start

### 1. Configure API Credentials

1. Launch the application
2. Navigate to **Settings** tab
3. Enter your FortiCloud API credentials (apiId and password)
4. Click **Test Connection** to verify
5. Click **Save Credentials** (Windows: encrypted storage, macOS: session-only)

### 2. Convert Excel to CSV

1. Navigate to **Convert** tab
2. Select your Excel file (.xlsx)
3. Choose output location for CSV
4. Select default host location
5. Click **Convert**

**Excel Format:**
- Group headers start with `#` (e.g., `# Web Servers`)
- Host rows: Name, IP Address, Type (optional), Location (optional)
- Maximum 35 characters per hostname

### 3. Import to FortiSASE

1. Navigate to **Import** tab
2. Select your CSV file
3. Choose group update mode:
   - **Ask**: Prompt for conflicts (safest)
   - **Merge**: Combine with existing groups
   - **Overwrite**: Replace existing members
4. Click **Start Import**
5. Monitor progress in real-time

### 4. Undo if Needed

Click **Undo Last Import** to rollback changes from the most recent import session.

## Troubleshooting

### Connection Test Fails
- Verify API credentials are correct
- Check network access to `customerapiauth.fortinet.com` and `portal.prod.fortisase.com`
- Check application logs (Help → Open Logs Folder)

### Import Errors
- **HTTP 401**: Invalid credentials or expired token
- **HTTP 429**: Rate limited (automatic retry enabled)
- **HTTP 409**: Host already exists (will be skipped)

### Name Warnings
- **Truncated**: Hostname exceeded 35 characters (domain removed first)
- **Invalid Characters**: Replaced with underscores
- **Duplicates**: Renamed with `-2`, `-3` suffix


Import times vary by file size and API rate limits:
- **< 500 hosts**: ~3-5 minutes
- **500-2,000 hosts**: ~15-30 minutes
- **2,000-5,000 hosts**: ~1-1.5 hours
- **5,000-10,000 hosts**: ~2-3 hours

**File Limits:**
- Soft warning at 5,000 rows
- Hard limit at 10,000 rows (split file recommended)

## Getting Help

- **Issues**: [Report bugs](https://github.com/gwilliamspro/FortiSASE-Made-Easy-Releases/issues)
- **Documentation**: Press F1 in app for context-sensitive help
- **Logs**: Help menu → Open Logs Folder

## License

Copyright © 2025. All rights reserved.

## Credits

Built with:
- .NET 8.0
- Avalonia UI (cross-platform framework)
- CommunityToolkit.Mvvm
- ClosedXML (Excel processing)
- CsvHelper
- Serilog

---

**Note**: This is the public releases repository. Source code is not publicly available.
