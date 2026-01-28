# Checksum Utilities

## Overview

Checksums (cryptographic hashes) verify file integrity by generating a unique fingerprint of file contents. Any modification to the file produces a different checksum.

## Common Algorithms

| Algorithm | Output Length | Status |
|-----------|---------------|--------|
| MD5 | 128 bits | Deprecated for security, still used for integrity |
| SHA-1 | 160 bits | Deprecated |
| SHA-256 | 256 bits | Recommended |
| SHA-512 | 512 bits | Recommended |

For evidence purposes, use **SHA-256** or stronger.

## Command Line Tools

### Linux/macOS

```bash
# Generate SHA-256 checksum
sha256sum myfile.zip

# Verify against known checksum
sha256sum -c checksums.txt

# Generate for multiple files
sha256sum *.zip > checksums.txt
```

### Windows

```powershell
# PowerShell
Get-FileHash myfile.zip -Algorithm SHA256

# Command Prompt
certutil -hashfile myfile.zip SHA256
```

## GUI Tools

### QuickHash GUI
- **Website**: https://www.quickhash-gui.org/
- **Platforms**: Windows, Linux, macOS
- **License**: Open source (GPLv2)
- **Description**: Feature-rich, cross-platform hashing tool designed for forensic use
- **Features**:
  - Hash individual files or entire folders
  - Compare files/folders
  - Recursive directory hashing
  - Copy files with hash verification
  - Base64 encoding/decoding
  - Supports MD5, SHA-1, SHA-256, SHA-512, xxHash

### Jacksum
- **Website**: https://jacksum.net/
- **Platforms**: Windows, Linux, macOS (Java-based)
- **License**: Open source (GPLv3)
- **Description**: Comprehensive checksum utility supporting over 400 hash algorithms
- **Features**:
  - Supports 470+ hash algorithms
  - GUI and command-line interfaces
  - File integrity verification
  - Hash file generation in multiple formats
  - Cross-platform via Java

### MD5-SHA Checksum Utility
- **Repository**: https://github.com/oop7/MD5-SHA-Checksum-Utility
- **Platforms**: Windows
- **License**: Open source
- **Description**: Simple, lightweight Windows utility for quick hash generation
- **Features**:
  - MD5, SHA-1, SHA-256, SHA-512
  - Drag-and-drop support
  - Compare against known hash
  - Minimal, easy-to-use interface

### Other Options
- **HashCheck** (Windows) - Shell extension
- **HashTab** (Windows) - File properties integration
- **GtkHash** (Linux) - GTK-based GUI

## Use for Evidence

1. Generate checksums immediately after creating evidence files
2. Store checksum files alongside evidence
3. Re-verify checksums when accessing files
4. Include checksums in documentation

Example workflow:
```bash
# After creating evidence archive
sha256sum evidence_2024-01-28.zip > evidence_2024-01-28.zip.sha256

# Later, verify integrity
sha256sum -c evidence_2024-01-28.zip.sha256
```

## Best Practices

- Use SHA-256 or SHA-512
- Generate checksums immediately after file creation
- Store checksums separately from files (different location/media)
- Document the checksum generation process
- Consider [OpenTimestamps](../timestamps/opentimestamps.md) for timestamped proof

## Related

- [OpenTimestamps](../timestamps/opentimestamps.md) - Timestamp your checksums
- [WORM Storage](../worm-media/) - Store files immutably
