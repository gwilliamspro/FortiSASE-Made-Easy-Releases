# Changelog

All notable changes to FortiSASE Made Easy will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.0] - 2025-11-10

### 🎉 First Official Stable Release!

FortiSASE Made Easy v1.0.0 is now production-ready with complete auto-update capability.

### What's New

**Windows Support:**
- ✅ Windows 10/11 (64-bit)
- ✅ Single-file executable deployment (no extraction required)
- ✅ Self-contained .NET 8.0 runtime (no dependencies to install)

**Auto-Update System:**
- Automatic update notifications on app startup (background checks)
- Manual "Check for Updates" option in Settings page
- Secure Ed25519 signature verification for all updates
- Non-blocking update checks - never interrupts your workflow

**Enhanced User Interface:**
- Full markdown rendering in help panels (Avalonia 11.3)
- Context-aware help drawer system (press F1)
- Real-time connection status indicator in status bar
- Improved progress synchronization across all operations

**Core Features:**
- Bulk import hosts and groups from Excel/CSV files
- Automatic hostname sanitization (35 character limit compliance)
- Flexible group management (Ask/Merge/Overwrite modes)
- Undo/rollback capability for failed imports
- Secure credential storage using Windows DPAPI
- Comprehensive logging with 7-day retention

### From Beta to Stable

This release marks the transition from pre-release (0.x.x) to production-ready (1.x.x). All features have been thoroughly tested with 206 passing unit tests.

**Previous Beta Releases:**
- v0.6.1 - Markdown rendering fix
- v0.6.0 - Auto-updater integration
- v0.5.1 - Progress synchronization improvements
- v0.5.0 - Drawer help system
- v0.4.0 - Bulk deletion feature
- v0.3.1 - Session persistence fixes
- v0.3.0 - IP validation
- v0.2.1 - HTTP 411 fix
- v0.2.0 - MVVM framework migration
- v0.1.1 - Critical bug fixes
- v0.1.0 - Initial MVP

### System Requirements

- **Operating System:** Windows 10/11 (64-bit)
- **Runtime:** None required (self-contained .NET 8.0 runtime included)
- **Memory:** 512 MB minimum
- **Disk Space:** 200 MB free space
- **Network:** Internet connection for FortiSASE API access

### Installation

1. Download `FortiSASE-Made-Easy-v1.0.0-win-x64.exe` from [Releases](https://github.com/gwilliamspro/FortiSASE-Made-Easy-Releases/releases/tag/v1.0.0)
2. Run the executable (no installation or extraction required)
3. Configure FortiCloud credentials in Settings tab
4. Start importing hosts!

**Note:** On first launch, the app may extract dependencies to a temporary folder. This is normal and only happens once.

### Auto-Update

Future versions will be automatically detected! The app will notify you when updates are available and guide you through installation.

---

## [0.5.1] - 2025-11-09

### Fixed
- Log window layout: Last log entry now fully visible with footer clearance
- Progress bar synchronization: Progress percentage now matches log entry count exactly
- Changed progress messages to past tense for better UX ("Created host X" vs "Creating...")

### Improved
- Footer height increased for better button visibility
- Real-time feedback accuracy during import and deletion operations

---

## [0.5.0] - 2025-11-08

### Added
- Context-aware help drawer accessible via F1 key
- Real-time global logs viewer (Ctrl+L to open)
- Import history browser showing recent import sessions
- Connection status indicator in status bar (green = connected)
- Configurable group header denotation in Convert tab

### Improved
- Streamlined inline help sections (moved to drawer system)
- Enhanced log visibility with color-coded severity levels
- Better authentication state tracking across all operations

---

## [0.4.0] - 2025-11-08

### Added
- CSV-based bulk host deletion feature
- Automatic group cleanup when removing hosts
- Remove tab with preview panel and cancellation support
- Connection state service for pre-flight validation

### Improved
- Group management: Groups auto-delete when all members removed
- Error handling: 404 errors handled gracefully during deletions

---

## [0.3.1] - 2025-11-07

### Fixed
- Import sessions now properly persisted to disk for undo functionality
- Undo operation dependency ordering (delete groups before hosts)
- API error messages now show detailed FortiSASE error text

### Added
- ImportSessionRepository for session storage abstraction
- Improved error parsing for better troubleshooting

---

## [0.3.0] - 2025-11-07

### Added
- IP address validation using IPAddress.TryParse()
- Dual warning system: post-conversion AND pre-import warnings
- Hard limit of 10,000 hosts with import blocking for oversized files

### Fixed
- Invalid IP addresses (e.g., 999.x.x.x, 256.x.x.x) now properly rejected
- Large file warnings now display correctly on both Convert and Import pages

### Improved
- CSV validation shows errors immediately when file is selected
- 28 new unit tests for IP validation edge cases

---

## [0.2.1] - 2025-11-07

### Fixed
- HTTP 411 "Length Required" error when authenticating with FortiCloud API
- Replaced chunked transfer encoding with explicit Content-Length headers

### Improved
- OAuth2 token management now fully functional
- All API operations now work reliably

---

## [0.2.0] - 2025-11-07

### Changed
- Migrated MVVM framework from ReactiveUI to CommunityToolkit.Mvvm
- Reduced ViewModel boilerplate code by 14% (161 lines)
- All ViewModels now use source generator attributes

### Fixed
- UI threading violations in Progress<T> callbacks
- Improved UI responsiveness during background operations

### Technical
- Removed ReactiveUI dependencies
- Better integration with Avalonia's threading model

---

## [0.1.1] - 2025-11-07

### Fixed
- Application crash after async operations ("Call from invalid thread" error)
- Missing ReactiveUI scheduler initialization
- Excel parser now handles data in Column B (previously only Column A)

### Added
- 5 new unit tests for flexible Excel layouts

---

## [0.1.0] - 2025-11-07

### Added
- Initial MVP release
- Excel to CSV conversion with hostname sanitization
- Bulk import via FortiSASE REST API
- Group management (Ask/Merge/Overwrite modes)
- Undo/rollback capability
- OAuth2 authentication with token refresh
- Secure credential storage (Windows DPAPI)
- Real-time logging and progress tracking
- Comprehensive error handling and retry logic

### Features
- Settings tab: Credential management
- Convert tab: Excel to CSV conversion
- Import tab: Bulk import with group management
- 105 unit tests (100% pass rate)
- Cross-platform support (Windows primary, Linux/macOS basic)

---

## How to Use This Changelog

### Version Numbering

This project follows [Semantic Versioning](https://semver.org/):
- **0.y.z** = Pre-release versions (current phase)
- **1.0.0** = First official stable release
- **MAJOR.MINOR.PATCH** format:
  - MAJOR = Breaking changes
  - MINOR = New features (backward compatible)
  - PATCH = Bug fixes only

### Upgrade Notes

When upgrading between versions:
1. Close the application
2. Download the new `.exe` file
3. Run the new executable
4. Settings and credentials are preserved (stored in AppData)

**Note:** You can delete old executable files after upgrading - your data is stored separately in AppData.

---

**For detailed technical changes, see the [private development repository](https://github.com/gwilliamspro/FortiSASE-Made-Easy)** (access restricted).
