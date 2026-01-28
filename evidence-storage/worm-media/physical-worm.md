# Physical WORM Media

**Platform:** Hardware
**Type:** Write-Once Storage Media
**Cost:** Varies by media type

## Overview

Physical WORM (Write Once, Read Many) media provides offline, tamper-evident storage for evidence archives.

## Media Types

### Optical Media

**M-DISC (Millennial Disc)**
- Designed for archival longevity (claimed 1000+ years)
- Available in DVD and Blu-ray formats
- Requires M-DISC compatible burner
- Cannot be overwritten or erased

**Standard DVD-R / BD-R**
- Write-once by design
- Shorter lifespan than M-DISC
- Widely available and inexpensive
- Store in cool, dark, dry conditions

### Tape

**LTO WORM Tapes**
- Enterprise-grade archival storage
- High capacity
- Requires LTO tape drive
- Used in legal and medical archival

## Advantages

- No ongoing service costs
- Not dependent on cloud provider
- Physical possession provides control
- Can be stored in secure locations (safe deposit box, etc.)
- No internet connectivity required

## Disadvantages

- Media degradation over time (varies by type)
- Requires compatible hardware to read
- Manual process
- Storage environment matters

## Best Practices

- Use quality media (M-DISC for longevity)
- Create multiple copies
- Store in different physical locations
- Include checksums on the media
- Label clearly with date and contents
- Verify readability periodically

## Related

- [AWS S3 Object Lock](aws-s3-object-lock.md) - Cloud WORM alternative
- [Checksum Utilities](../checksums/overview.md) - Verify data integrity
