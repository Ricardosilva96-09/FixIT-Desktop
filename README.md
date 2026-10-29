# FixIT Desktop

**Windows diagnostics and maintenance, developed by Ricardo Silva.**

FixIT Desktop brings system checks, guided maintenance and local reporting together in a clean desktop interface built with C# and WPF.

**Current release: 1.2.1 Beta**

[Download and release notes](https://github.com/Ricardosilva96-09/FixIT-Desktop/releases)

## Features

### Dashboard and Health Score

View CPU and memory usage, graphics hardware identification, system disk usage and administrator status.

The Health Score evaluates available security, updates, disk space and Windows integrity results. Scan coverage is shown separately: a high score with partial coverage does not mean the entire computer has been verified.

Scores become outdated after maintenance changes and require a new scan.

### Smart Scan

Check available information about:

- Microsoft Defender and Windows Firewall.
- Pending Windows software updates.
- Device errors and drivers requiring review.
- Windows image integrity.
- Disk space and eligible temporary files.
- Empty folders and broken shortcuts.
- Startup applications.
- Recent Windows errors and crashes.

Unavailable or inaccessible information is marked as **unconfirmed**.

### Guided Corrections

Review actions based on the current scan results, confirm them and follow their progress.

Supported actions include eligible temporary-file cleanup, removal of selected empty folders or broken shortcuts, installation of identified Windows software updates and Windows repair when applicable.

Folder and shortcut removal requires manual selection. Drivers are excluded from automatic installation, and Windows restarts are not forced.

### Startup Manager

Enable or disable supported startup entries, search applications and review recommendations with source links.

Changes require confirmation. Unknown entry formats are preserved, and some entries require administrator privileges.

### Cleanup

- Remove eligible temporary files older than 24 hours.
- Select empty folders for removal.
- Remove selected shortcuts whose targets remain missing.
- Manually repair a shortcut target, with a backup of the original.
- Inspect and optionally clean Windows Prefetch.

Prefetch cleanup is separate from general corrections. Windows rebuilds this cache, and clearing it can temporarily slow subsequent launches.

### Windows Repair

Run explained Windows maintenance commands:

- DISM CheckHealth
- DISM ScanHealth
- DISM RestoreHealth
- SFC /scannow

The application checks administrator privileges, requests confirmation and displays command output.

### Diagnostics

Explore hardware, storage, network, security, updates and Windows events.

Additional diagnostics cover battery information, OneDrive, printers, shared folders, Windows VPN profiles and physical disks, where Windows exposes the required data.

### Reports and Settings

- Persistent scan history and activity records.
- JSON and HTML export.
- Printable reports, including PDF through the Windows print dialog.
- Read-only viewing of saved reports.
- Portuguese and English interface.
- Configurable interface scale, metric refresh interval and report retention.

## Requirements

- Windows 10 or Windows 11, 64-bit.
- .NET Framework 4.8 for the launcher, normally included with current Windows versions.
- Administrator privileges for certain maintenance operations.
- Internet access for Windows Update downloads.

The application includes its .NET 10 runtime. Python and a separate .NET SDK installation are not required to run the distributed package.

## Download and Run

1. Open the [Releases page](https://github.com/Ricardosilva96-09/FixIT-Desktop/releases).
2. Download `FixIT_Desktop_RicardoSilva_v1.2.1.zip`.
3. Extract the entire archive into a new folder.
4. Open `FixIT.Desktop.exe`.

Keep the `runtime` folder alongside the executable.

To replace an older version, close it first and extract the new release into a separate folder. Avoid mixing files from different versions.

## Privacy and Local Data

Settings, activity records, reports and shortcut backups are stored locally under:

```text
%LOCALAPPDATA%\FixITDesktop\WPF
```

Reports may contain hardware information, application names and local paths. Review them before sharing, or choose to omit details during export.

Windows Update and explicitly requested connectivity tests may contact external services.

## Beta Status and Limitations

This is a beta release.

Some diagnostics depend on Windows edition, system policies, hardware support and permissions. Temperatures, GPU metrics and other measurements may be unavailable.

An old driver date does not prove that an update exists. Event-log explanations are investigation suggestions rather than definitive diagnoses.

The application is not signed with a trusted code-signing certificate. Windows may display security warnings or restrict execution according to its protection settings.

## Testing

Version 1.2.1 passed **63 automated checks**, covering cleanup safeguards, cancellation, simulated startup changes, report validation, history handling and shortcut repair.

Native shortcut tests used files created specifically for testing. Interface checks covered Portuguese and English.

Real Windows repairs, update installations and changes to existing startup applications were not performed during validation. Some diagnostic queries were restricted by the test environment.

The package includes `AUDITORIA.md` with further validation details.

## Reporting Issues

Open an issue in this repository and include:

- Your Windows version.
- Your FixIT Desktop version.
- Steps to reproduce the problem.
- The error message and a screenshot, if available.

Remove personal information before uploading screenshots or reports.

## Development

FixIT Desktop uses **C#**, **WPF** and **.NET 10**.

The distributed package includes a `Source` folder with the project, resources, tests and build scripts. See its README for build instructions.

## Author

**Ricardo Silva**

© 2026 Ricardo Silva.
