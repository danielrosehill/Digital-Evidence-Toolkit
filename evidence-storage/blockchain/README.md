# Blockchain-Based Evidence Tools

Blockchain technology provides immutable, timestamped records that can strengthen evidence chain of custody. Once data is recorded on a blockchain, it cannot be altered without detection.

## Why Blockchain for Evidence?

- **Immutability** - Records cannot be changed after being written
- **Timestamps** - Cryptographic proof that data existed at a specific time
- **Decentralisation** - No single point of failure or control
- **Transparency** - Anyone can verify the record independently
- **Longevity** - Major blockchains (Bitcoin, Ethereum) are likely to persist for decades

## Timestamping Services

### OpenTimestamps
- **Website**: https://opentimestamps.org/
- **Blockchain**: Bitcoin
- **Cost**: Free
- **Description**: Anchors document hashes to the Bitcoin blockchain
- **See**: [Detailed guide](timestamps/opentimestamps.md)

### OriginStamp
- **Website**: https://originstamp.com/
- **Blockchains**: Bitcoin, Ethereum
- **Cost**: Free tier available, paid plans for volume
- **Description**: Timestamp API and web interface for proving document existence
- **Features**:
  - Web upload or API integration
  - Email notifications
  - Certificate generation
  - Multi-blockchain anchoring

### Chainpoint
- **Website**: https://chainpoint.org/
- **Description**: Open standard for anchoring data to blockchains
- **Features**:
  - Generates Chainpoint proofs
  - Can anchor to multiple blockchains
  - Open protocol (not a single service)

## Notarisation Platforms

### Proof of Existence
- **Website**: https://proofofexistence.com/
- **Blockchain**: Bitcoin
- **Description**: One of the earliest blockchain notarisation services
- **Use Case**: Simple document timestamping with Bitcoin

### Notarize (Blockchain-enabled)
- **Website**: https://www.notarize.com/
- **Description**: Online notarisation with blockchain audit trails
- **Note**: Primarily for legal documents, may require identity verification

## Evidence-Specific Platforms

### Bernstein
- **Website**: https://www.bernstein.io/
- **Description**: IP and evidence management with blockchain certification
- **Use Case**: Intellectual property protection, trade secrets

### Veripart
- **Description**: Supply chain and evidence tracking on blockchain
- **Use Case**: Physical evidence chain of custody

## How to Use Blockchain for Evidence

### Basic Workflow

1. **Create evidence** (photo, document, recording)
2. **Calculate hash** (SHA-256)
3. **Submit hash to blockchain service**
4. **Store the proof/receipt**
5. **Archive original file** with proof

### Example with OpenTimestamps

```bash
# Install OpenTimestamps client
pip install opentimestamps-client

# Create timestamp for evidence file
ots stamp evidence.zip

# This creates evidence.zip.ots (the proof file)

# Later, verify the timestamp
ots verify evidence.zip.ots
```

## Limitations

- **Hash only** - Blockchain stores hashes, not actual files (file storage requires IPFS or similar)
- **Confirmation time** - Bitcoin blocks take ~10 minutes; full security requires multiple confirmations
- **Not legal proof everywhere** - Blockchain timestamps may not be legally recognised in all jurisdictions
- **Requires original file** - The proof is useless without the original file to verify against

## Best Practices

1. **Use established blockchains** - Bitcoin and Ethereum have the strongest security guarantees
2. **Keep proof files safe** - Store .ots or proof files alongside your evidence
3. **Verify proofs work** - Test verification before relying on timestamps
4. **Combine with other methods** - Blockchain is one layer; also use checksums, WORM storage, etc.
5. **Document the process** - Record which service you used and when

## Related

- [OpenTimestamps](timestamps/opentimestamps.md) - Detailed OpenTimestamps guide
- [IPFS](ipfs.md) - Decentralised file storage
- [Checksums](checksums/overview.md) - Hash generation
