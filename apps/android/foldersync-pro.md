# FolderSync Pro

**Platform:** Android
**Type:** File Synchronization
**Cost:** Paid (~$5)

## Overview

FolderSync Pro is an Android application for automated file synchronization between your device and cloud storage providers. It supports syncing to multiple destinations simultaneously, making it useful for the [Original and Working Evidence](../../best-practices.md) workflow.

## Key Features

- Sync to multiple cloud providers simultaneously
- Scheduled automatic sync
- Support for numerous cloud services (Google Drive, Dropbox, S3, WebDAV, etc.)
- Folder pair configuration
- Tasker integration for automation
- Filter rules for selective sync

## Supported Cloud Services

- Google Drive
- Dropbox
- OneDrive
- Amazon S3 (and S3-compatible like Wasabi)
- Box
- SFTP/FTP
- WebDAV
- Many others

## Use for Evidence

FolderSync Pro enables parallel upload to two destinations:

1. **Leg 1 (Immutable):** Sync ProofMode archives to S3 with Object Lock
2. **Leg 2 (Working):** Sync same archives to Google Drive for extraction

This creates automatic redundancy with one copy in tamper-proof storage and one for working use.

## Example Configuration

### Folder Pair 1: WORM Storage
- **Local folder:** `/ProofMode/exports/`
- **Remote:** S3 bucket with Object Lock
- **Sync type:** Upload only

### Folder Pair 2: Working Storage
- **Local folder:** `/ProofMode/exports/`
- **Remote:** Google Drive
- **Sync type:** Upload only

## Installation

- [Google Play Store](https://play.google.com/store/apps/details?id=dk.tacit.android.foldersync.full)

## Alternatives

- **FolderSync (Free)** - Limited version with fewer accounts
- **Autosync** - Similar functionality
- **Syncthing** - Open source, device-to-device sync

## Related

- [Best Practices](../../best-practices.md) - Original and Working Evidence workflow
- [AWS S3 Object Lock](../../evidence-storage/worm-media/aws-s3-object-lock.md) - WORM storage destination
