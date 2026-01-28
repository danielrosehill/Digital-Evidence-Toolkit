# ProofMode

**Platform:** Android
**Type:** Mobile Application
**Cost:** Free / Open Source

## Overview

ProofMode is an Android application that captures photos and videos with cryptographic verification and metadata preservation.

## Key Features

- Automatic metadata embedding (GPS, timestamp, device info)
- Cryptographic signatures
- Hash generation for integrity checking
- Export as verifiable archive bundles
- Open source

## Installation

- [Google Play Store](https://play.google.com/store/apps/details?id=org.witness.proofmode)
- [F-Droid](https://f-droid.org/packages/org.witness.proofmode/)
- [GitHub](https://github.com/nicksellen/proofmode-android)

## Workflow Integration

ProofMode exports evidence as ZIP archives containing the media plus verification data. These archives work well with the [Original and Working Evidence](../best-practices.md) workflow:

1. Capture with ProofMode
2. Export archive
3. Sync to WORM storage (original) and working storage (for extraction)

## References

- [Guardian Project](https://guardianproject.info/apps/org.witness.proofmode/)
- [ProofMode Documentation](https://proofmode.org/)

## Related

- [Capture Cam](capture-cam.md) - Alternative with blockchain verification
- [Content Authenticity Initiative](../photo-video/content-authenticity.md) - Hardware-level alternatives
