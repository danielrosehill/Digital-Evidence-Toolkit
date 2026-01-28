# Rclone

**Type:** Cloud Storage Sync Tool
**Platforms:** Windows, Linux, macOS
**Cost:** Free, open source
**Website:** https://rclone.org/

## Overview

Rclone is a command-line tool for managing and syncing files to cloud storage. Often described as "rsync for cloud storage," it supports over 70 cloud storage providers and is essential for evidence backup workflows.

## Key Features

- Sync files to/from cloud storage
- Supports 70+ providers (S3, Google Drive, Dropbox, OneDrive, Backblaze, Wasabi, etc.)
- Encryption support (encrypt files before upload)
- Bandwidth limiting
- Checksum verification during transfers
- Mount cloud storage as local filesystem
- Server-side copy between providers

## Why Use for Evidence Storage

- **Multi-destination sync** - Upload evidence to multiple cloud providers simultaneously
- **Integrity verification** - Built-in checksum verification ensures files transfer correctly
- **Encryption** - Encrypt evidence before uploading to untrusted storage
- **Automation** - Script evidence backup workflows
- **S3 Object Lock support** - Works with immutable storage providers

## Basic Usage

```bash
# Configure a remote (interactive setup)
rclone config

# Sync local folder to cloud
rclone sync /path/to/evidence remote:bucket/evidence

# Copy with progress
rclone copy /path/to/evidence remote:bucket/evidence --progress

# Verify files match
rclone check /path/to/evidence remote:bucket/evidence

# Mount cloud storage locally
rclone mount remote:bucket /mnt/cloud
```

## Evidence Workflow Example

```bash
# Upload evidence to immutable S3 storage
rclone copy ./evidence-archives s3-worm:evidence-bucket/ \
  --checksum \
  --progress \
  --log-file=upload.log

# Verify upload integrity
rclone check ./evidence-archives s3-worm:evidence-bucket/
```

## GUI Option: Rclone UI

For users who prefer a graphical interface:

### Rclone UI
- **Repository**: https://github.com/rclone-ui/rclone-ui
- **Description**: Modern web-based GUI for rclone
- **Features**:
  - Visual remote configuration
  - File browser interface
  - Transfer progress monitoring
  - Job management
  - Easier setup for non-technical users

## Configuration Tips

1. **Use encryption** for sensitive evidence on shared/untrusted storage
2. **Enable checksums** (`--checksum`) for all evidence transfers
3. **Log transfers** (`--log-file`) for audit trail
4. **Test restores** periodically to verify backups work

## Related

- [AWS S3 Object Lock](../worm-media/aws-s3-object-lock.md) - Immutable storage destination
- [Best Practices](../../guides/best-practices.md) - Evidence workflow recommendations
