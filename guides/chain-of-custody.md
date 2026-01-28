# Chain of Custody

Chain of custody is the documented, unbroken trail that records the sequence of custody, control, transfer, analysis, and disposition of evidence. It establishes that evidence has not been tampered with and can be trusted as authentic.

## Why It Matters

Without a proper chain of custody:
- Evidence may be deemed inadmissible in court
- Opposing parties can argue evidence was fabricated or altered
- The credibility of your entire case may be undermined

A strong chain of custody demonstrates:
- **When** evidence was created
- **Who** has handled it
- **What** was done to it at each stage
- **How** it was protected from tampering

---

## The Evidence Lifecycle

```
┌─────────────────────────────────────────────────────────────────────────┐
│                        CHAIN OF CUSTODY WORKFLOW                         │
└─────────────────────────────────────────────────────────────────────────┘

    ┌──────────────┐
    │   CAPTURE    │  Take photo, record audio, save screenshot, etc.
    │              │
    │  Use app with│  ─── ProofMode, Capture Cam, Content Authenticity
    │  built-in    │      devices automatically handle steps 2-4
    │  verification│
    └──────┬───────┘
           │
           │ If using standard camera/recorder:
           ▼
    ┌──────────────┐
    │  CALCULATE   │  Generate cryptographic hash immediately
    │  CHECKSUM    │
    │              │  ─── SHA-256 recommended (sha256sum on Linux/Mac)
    │              │      MD5 acceptable but weaker
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │  TIMESTAMP   │  Prove the file existed at a specific time
    │              │
    │              │  ─── OpenTimestamps (blockchain-anchored)
    │              │      Trusted timestamping services
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │   STORE      │  Save to tamper-proof storage
    │  IMMUTABLY   │
    │              │  ─── AWS S3 Object Lock
    │              │      WORM media (optical disc, tape)
    │              │      Immutable cloud storage
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │  DOCUMENT    │  Record all handling in a log
    │  HANDLING    │
    │              │  ─── Who accessed it and when
    │              │      Any copies made
    │              │      Analysis performed
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │   VERIFY     │  Before presenting evidence
    │              │
    │              │  ─── Recalculate checksum, compare to original
    │              │      Verify timestamp is valid
    │              │      Confirm storage audit logs
    └──────────────┘
```

---

## Two Paths: Automated vs Manual

### Path A: Using ProofMode or Similar Apps

Apps like [ProofMode](../apps/android/proofmode.md) automate the chain of custody:

1. **Capture** - Take photo/video through the app
2. **Automatic** - App generates checksums, captures GPS, timestamps, device info
3. **Automatic** - Cryptographic signatures applied
4. **Export** - Transfer the evidence bundle (includes all proofs)
5. **Store** - Save bundle to immutable storage

**Advantages**: Less manual work, harder to make mistakes, cryptographically signed

### Path B: Manual Chain of Custody

If you capture evidence with a standard camera or app:

1. **Capture** - Take the photo/video/screenshot
2. **Immediately calculate checksum**:
   ```bash
   # Linux/Mac
   sha256sum evidence_file.jpg > evidence_file.jpg.sha256

   # Windows PowerShell
   Get-FileHash evidence_file.jpg -Algorithm SHA256 | Out-File evidence_file.jpg.sha256
   ```
3. **Timestamp the checksum**:
   - Use [OpenTimestamps](../evidence-storage/timestamps/opentimestamps.md)
   - Or a trusted timestamping authority
4. **Store immutably**:
   - Upload to S3 with Object Lock
   - Burn to write-once optical media
   - Use immutable cloud storage
5. **Document everything**:
   - Create a handling log (see template below)

---

## Handling Log Template

Maintain a written record for each piece of evidence:

```
EVIDENCE HANDLING LOG
=====================

Evidence ID: [unique identifier]
Original filename:
Description:
Captured by:
Capture date/time:
Capture device:
Capture location (if applicable):

Original checksum (SHA-256):

HANDLING RECORD
---------------
Date/Time          | Person      | Action                    | Notes
-------------------|-------------|---------------------------|------------------
2025-01-28 14:30   | J. Smith    | Evidence captured         | Using iPhone 15
2025-01-28 14:32   | J. Smith    | Checksum calculated       | SHA-256: abc123...
2025-01-28 14:35   | J. Smith    | Timestamped               | OpenTimestamps
2025-01-28 15:00   | J. Smith    | Uploaded to S3            | Object Lock enabled
2025-01-29 09:00   | A. Jones    | Accessed for review       | Checksum verified
```

---

## Verification Checklist

Before presenting evidence, verify:

- [ ] Original file checksum matches recorded checksum
- [ ] Timestamp proof is valid and verifiable
- [ ] Storage audit logs show no unauthorized access
- [ ] Handling log is complete and consistent
- [ ] All copies can be traced back to the original

---

## Glossary

| Term | Definition |
|------|------------|
| **Chain of Custody** | The documented trail showing who has handled evidence and what was done to it |
| **Checksum / Hash** | A cryptographic fingerprint of a file; any change to the file produces a different hash |
| **SHA-256** | Secure Hash Algorithm producing a 256-bit hash; current industry standard |
| **MD5** | Older hash algorithm; still used but considered cryptographically weak |
| **Timestamp** | Cryptographic proof that a file existed at a specific point in time |
| **OpenTimestamps** | Free, open protocol for creating blockchain-anchored timestamps |
| **WORM** | Write Once, Read Many - storage that cannot be modified after writing |
| **Object Lock** | Cloud storage feature (e.g., AWS S3) that prevents deletion or modification |
| **Immutable Storage** | Storage where data cannot be changed or deleted for a specified period |
| **Cryptographic Signature** | Mathematical proof that data was created by a specific entity |
| **Metadata** | Data about data - timestamps, GPS coordinates, device info embedded in files |
| **EXIF** | Exchangeable Image File Format - metadata standard for images |
| **Forensic Copy** | Bit-for-bit duplicate of original evidence |
| **Evidence Bundle** | Package containing evidence file plus all verification materials |
| **Audit Log** | Record of all access and actions taken on stored evidence |
| **Tamper-Evident** | System designed to reveal if unauthorized changes were attempted |
| **Non-Repudiation** | Proof that prevents someone from denying they created or handled evidence |
| **Digital Forensics** | Scientific examination of digital devices and data for legal purposes |
| **Provenance** | The origin and history of a piece of evidence |

---

## Related Pages

- [OpenTimestamps](../evidence-storage/timestamps/opentimestamps.md) - Blockchain timestamping
- [Checksum Utilities](../evidence-storage/checksums/overview.md) - Hash calculation tools
- [ProofMode](../apps/android/proofmode.md) - Automated evidence capture app
- [WORM Storage](../evidence-storage/worm-media/) - Immutable storage options
- [Best Practices](best-practices.md) - General evidence handling guidelines
