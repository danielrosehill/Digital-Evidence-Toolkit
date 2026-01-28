# OpenTimestamps

**Platform:** Cross-platform
**Type:** Decentralized Timestamping
**Cost:** Free

## Overview

OpenTimestamps is a protocol for creating timestamps anchored to the Bitcoin blockchain, providing decentralized proof that data existed at a certain point in time.

## How It Works

1. You provide a hash of your file
2. OpenTimestamps aggregates hashes into a Merkle tree
3. The Merkle root is embedded in a Bitcoin transaction
4. You receive a timestamp proof file (.ots)
5. Anyone can verify the proof against the blockchain

## Key Features

- Decentralized (no trusted third party)
- Immutable (anchored to Bitcoin blockchain)
- Free to use
- Open source
- Verifiable by anyone

## Installation

### Command Line Client

```bash
pip install opentimestamps-client
```

### Usage

```bash
# Create timestamp
ots stamp myfile.zip

# Verify timestamp (after blockchain confirmation)
ots verify myfile.zip.ots
```

### Web Interface

[OpenTimestamps.org](https://opentimestamps.org/) provides a web-based stamping interface.

## Use for Evidence

Timestamping evidence files proves they existed at the time of stamping:

1. Generate checksum of evidence archive
2. Stamp the archive (or the checksum file)
3. Store the .ots proof file alongside the evidence
4. Verification confirms the file existed at that time

## Considerations

- Timestamp confirmation requires Bitcoin block confirmation (can take hours)
- Proves existence at a time, not authenticity of content
- Store .ots files securely alongside evidence
- Verify timestamps work before relying on them

## References

- [OpenTimestamps Website](https://opentimestamps.org/)
- [GitHub Repository](https://github.com/opentimestamps/opentimestamps-client)
