# Best Practices for Digital Evidence Collection

**Disclaimer:** These are suggested methods, not legal advice. Adapt these workflows to your own needs and circumstances.

> **AI Disclosure:** This guide was developed with the assistance of Claude Code, an AI coding assistant by Anthropic.

## Workflow: Original and Working Evidence

One approach to evidence management is maintaining **two parallel storage paths**:

1. **Original Evidence (Immutable)** - Untouched archives in WORM storage for chain of custody
2. **Working Evidence** - Extracted copies for practical use in documents, reports, and sharing

This separation ensures you always have pristine originals while still being able to work with the evidence.

## Recommended Workflow

### Step 1: Capture Evidence

Use tools like [ProofMode](android-apps/proofmode.md) or [Capture Cam](android-apps/capture-cam.md) to capture photos and videos with embedded metadata and cryptographic signatures.

### Step 2: Parallel Upload

Use a synchronization tool like **FolderSync Pro** (Android) to automatically upload evidence bundles to two destinations simultaneously:

#### Leg 1: Immutable Storage (WORM)
- Upload the complete, unmodified ProofMode archive (ZIP file)
- Destination: [AWS S3 with Object Lock](evidence-storage/worm-media/aws-s3-object-lock.md) or equivalent WORM storage
- **Never modify or extract from this copy**
- This is your chain of custody archive

#### Leg 2: Working Storage
- Upload the same archive to working cloud storage (e.g., Google Drive)
- This copy is for extraction and practical use

### Step 3: Extract Working Copies

On the working storage side, use scripts to:
- Extract photos and videos from ProofMode archives
- Organize into date-based or case-based subfolders
- Generate working copies for document creation

Example extraction script concept:
```bash
# Extract ProofMode archives to organized subfolders
for archive in *.zip; do
    folder_name="${archive%.zip}"
    mkdir -p "extracted/$folder_name"
    unzip "$archive" -d "extracted/$folder_name"
done
```

### Step 4: Use Working Copies

From your working storage, you can:
- Create reports and documents
- Share specific items with legal counsel
- Prepare exhibits
- Annotate copies (never originals)

## Why This Workflow Matters

| Concern | How This Workflow Addresses It |
|---------|-------------------------------|
| Tampering accusations | Original WORM archive proves no modification |
| Chain of custody | Immutable storage with timestamps |
| Practical usability | Working copies allow normal file operations |
| Accidental modification | Originals are write-protected |
| Backup redundancy | Two independent copies in different systems |

## Tool Recommendations

### Capture
- [ProofMode](photo-video/proofmode.md) - Photo/video with crypto signatures
- [ASR](audio-recording/asr-android.md) or [Sony ICD](audio-recording/sony-icd-series.md) - Audio

### Synchronization
- **FolderSync Pro** (Android) - Automated sync to multiple cloud destinations
- **rclone** (Desktop) - Command-line cloud sync tool

### Immutable Storage
- [AWS S3 Object Lock](evidence-storage/worm-media/aws-s3-object-lock.md)
- [Physical WORM Media](evidence-storage/worm-media/physical-worm.md)
- Wasabi with Object Lock

### Working Storage
- Google Drive
- Dropbox
- OneDrive
- Self-hosted (with proper backup)

### Integrity Verification
- [Checksum Utilities](evidence-storage/checksums/overview.md)
- [OpenTimestamps](evidence-storage/timestamps/opentimestamps.md)

## Additional Best Practices

### At Capture Time
1. Ensure accurate device time (sync with network time)
2. Enable GPS/location if relevant and appropriate
3. Capture more context than you think you need
4. Note environmental details mentally for later documentation

### Immediately After Capture
1. Trigger sync to both storage destinations
2. Verify uploads completed successfully
3. Do not delete from device until confirmed in WORM storage

### For Long-Term Storage
1. Generate checksums of all archives
2. Consider [OpenTimestamps](evidence-storage/timestamps/opentimestamps.md) for blockchain-anchored timestamps
3. Document your storage procedures
4. Test restoration periodically

### Documentation
1. Maintain a log of evidence collection activities
2. Record device information used for capture
3. Note any relevant circumstances
4. Keep records of storage locations and access

## Common Mistakes to Avoid

- **Editing originals** - Always work on copies
- **Single storage location** - Redundancy is essential
- **Delayed backup** - Sync immediately after capture
- **Poor organization** - Consistent naming and folder structure matter
- **No checksums** - Integrity verification supports authenticity claims
- **Forgetting metadata** - Preserve all original metadata
