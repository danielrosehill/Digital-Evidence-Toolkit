# IPFS (InterPlanetary File System)

**Type:** Decentralised Storage Network
**Cost:** Free (self-hosted) or paid pinning services
**Website:** https://ipfs.tech/

## Overview

IPFS is a peer-to-peer distributed file system that provides content-addressed storage. Files are identified by their cryptographic hash (CID), meaning the address itself verifies the content's integrity.

## Why Use IPFS for Evidence?

- **Content addressing** - File hash is the address; any change creates a different address
- **Built-in integrity** - If someone gives you a CID, retrieving it guarantees you get the exact file
- **Redundancy** - Files can be stored across multiple nodes worldwide
- **Censorship resistance** - No single point of control can remove content
- **Permanence** - Pinned content persists as long as at least one node hosts it

## How It Works

1. Add a file to IPFS
2. IPFS generates a Content Identifier (CID) based on the file's hash
3. The file is available at that CID from any IPFS node
4. Anyone with the CID can retrieve and verify the exact file

```bash
# Add file to IPFS
ipfs add evidence.zip
# Output: added QmXnnyufdzAWL5CqZ2RnSNgPbvCc1ALT73s6epPrRnZ1Xy evidence.zip

# Retrieve file using CID
ipfs get QmXnnyufdzAWL5CqZ2RnSNgPbvCc1ALT73s6epPrRnZ1Xy
```

## Getting Started

### Installation

**Linux:**
```bash
# Download and install
wget https://dist.ipfs.tech/kubo/v0.24.0/kubo_v0.24.0_linux-amd64.tar.gz
tar -xvzf kubo_v0.24.0_linux-amd64.tar.gz
cd kubo
sudo bash install.sh

# Initialise
ipfs init

# Start daemon
ipfs daemon
```

**Desktop Apps:**
- **IPFS Desktop** - https://docs.ipfs.tech/install/ipfs-desktop/
- GUI application for Windows, macOS, Linux

### Basic Commands

```bash
# Add a file
ipfs add myfile.pdf

# Add a directory
ipfs add -r evidence-folder/

# Pin content (keep it available)
ipfs pin add QmCID...

# View pinned content
ipfs pin ls
```

## Pinning Services

For evidence that must remain available long-term, use a pinning service (your local node may go offline):

### Pinata
- **Website**: https://www.pinata.cloud/
- **Free Tier**: 1 GB
- **Features**: Web interface, API, dedicated gateways

### Web3.Storage
- **Website**: https://web3.storage/
- **Free Tier**: Generous free allowance
- **Features**: Also stores on Filecoin for redundancy

### Filebase
- **Website**: https://filebase.com/
- **Features**: S3-compatible API, multi-network pinning

### Infura IPFS
- **Website**: https://www.infura.io/product/ipfs
- **Features**: API access, dedicated gateways

## Evidence Workflow with IPFS

### Recommended Process

1. **Capture evidence** and calculate local checksum
2. **Add to IPFS** - get the CID
3. **Pin with a service** - ensure long-term availability
4. **Record the CID** - store in your evidence log
5. **Timestamp the CID** - use OpenTimestamps on the CID for time proof
6. **Also store conventionally** - IPFS is an additional layer, not a replacement

### Example Script

```bash
#!/bin/bash
# Add evidence to IPFS and timestamp

FILE=$1
HASH=$(sha256sum "$FILE" | cut -d' ' -f1)

# Add to IPFS
CID=$(ipfs add -q "$FILE")

echo "File: $FILE"
echo "SHA-256: $HASH"
echo "IPFS CID: $CID"
echo "Gateway URL: https://ipfs.io/ipfs/$CID"

# Create timestamp proof
ots stamp "$FILE"

# Log the record
echo "$(date -Iseconds),$FILE,$HASH,$CID" >> evidence-log.csv
```

## Accessing IPFS Content

Files can be accessed via:

- **Local node**: `ipfs cat QmCID...`
- **Public gateways**: `https://ipfs.io/ipfs/QmCID...`
- **Dedicated gateways**: From pinning services

### Public Gateways

- https://ipfs.io/ipfs/
- https://dweb.link/ipfs/
- https://cloudflare-ipfs.com/ipfs/
- https://gateway.pinata.cloud/ipfs/

## Considerations

### Advantages
- Content-addressed = built-in integrity verification
- Decentralised = no single point of failure
- Free to use (just need a node)
- Pairs well with blockchain timestamps

### Limitations
- **Not private by default** - Anyone with the CID can access the file
- **Requires pinning** - Unpinned content may disappear
- **Not immutable storage** - You can unpin/delete from your node
- **Gateway reliability** - Public gateways may be slow or unavailable

### Privacy Note

IPFS content is public by default. For sensitive evidence:
- Encrypt files before adding to IPFS
- Use private IPFS networks
- Consider whether public availability is appropriate

## Combining with Other Tools

| Layer | Tool | Purpose |
|-------|------|---------|
| Integrity | SHA-256 checksum | Local verification |
| Distribution | IPFS | Content-addressed storage |
| Timestamp | OpenTimestamps | Proof of existence |
| Backup | S3 Object Lock | Immutable conventional storage |

## Related

- [Blockchain Tools](blockchain/README.md) - Timestamping and notarisation
- [OpenTimestamps](timestamps/opentimestamps.md) - Timestamp your CIDs
- [Checksums](checksums/overview.md) - Hash calculation
- [Cloud Storage](cloud-storage/) - Conventional storage options
