# PII Redaction & Anonymization

## Overview

When sharing or publishing evidence, you may need to redact personally identifiable information (PII) to protect privacy, comply with regulations, or focus on relevant details without exposing uninvolved parties.

## What to Redact

### Common PII Elements
- Names of uninvolved parties
- Phone numbers
- Email addresses
- Physical addresses
- Social security / national ID numbers
- Financial account numbers
- License plates
- Faces of bystanders
- Biometric identifiers

### Contextual PII
- Usernames that could identify someone
- Location data (GPS coordinates, landmarks)
- Device identifiers (IMEI, serial numbers)
- IP addresses
- Timestamps that reveal patterns

## Redaction Principles

1. **Redact copies, preserve originals** - Never modify original evidence
2. **Consistent redaction** - Same entity should be redacted the same way throughout
3. **Document what was redacted** - Keep a key mapping redactions to originals (secured separately)
4. **Verify completeness** - Check all instances were caught
5. **Consider metadata** - File metadata may contain PII too

## Redaction Methods

### Images
- Black boxes or solid color overlays
- Blur/pixelation (less secure - can sometimes be reversed)
- Complete removal of regions

### Documents
- PDF redaction tools (not just black highlighting)
- Export to image and redact
- Recreate document without PII

### Video
- Blur faces/regions
- Mute audio segments
- Overlay solid shapes

### Audio
- Silence/beep sensitive segments
- Pitch shifting (less effective)
- Transcript with redactions instead of audio

## Tools by Type

See individual tool pages:
- [Image Redaction Tools](image-redaction.md)
- [Video Redaction Tools](video-redaction.md)
- [Document Redaction Tools](document-redaction.md)
- [Audio Redaction](audio-redaction.md)

## Common Mistakes

1. **Using transparent highlight** - Text still visible/selectable
2. **Forgetting metadata** - EXIF, document properties still contain PII
3. **Inconsistent redaction** - Same name redacted in some places, not others
4. **Reversible methods** - Blur can sometimes be reversed
5. **Modifying originals** - Destroys evidence integrity
