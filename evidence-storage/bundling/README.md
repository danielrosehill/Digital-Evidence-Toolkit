# Evidence Bundling and Packaging

Tools for packaging, validating, and transferring digital evidence while maintaining integrity.

## BagIt Standard

BagIt is a hierarchical file packaging format designed for reliable storage and transfer of digital content. Originally developed by the Library of Congress.

### bagit-python
- **Repository**: https://github.com/LibraryOfCongress/bagit-python
- **Developer**: Library of Congress
- **Description**: Python library and command-line tool for working with BagIt packages
- **Features**:
  - Create bags from files/directories
  - Validate bag integrity
  - Generate and verify checksums (MD5, SHA-256, SHA-512)
  - Update bags after modifications

### Bagger
- **Repository**: https://github.com/LibraryOfCongress/bagger
- **Developer**: Library of Congress
- **Description**: GUI application for creating and validating BagIt packages
- **Features**:
  - Graphical interface for bag creation
  - Profile support for custom metadata
  - Batch processing capabilities
  - Cross-platform (Java-based)

## Evidence-Specific Tools

### CodeGuard Action
- **Repository**: https://github.com/DNYoussef/codeguard-action
- **Description**: GitHub Action for code integrity verification
- **Use Case**: Ensuring code evidence hasn't been tampered with in version control

### Claude Evidence Assistant
- **Repository**: https://github.com/danielrosehill/Claude-Evidence-Assistant
- **Description**: AI-assisted evidence documentation and organisation tool
- **Use Case**: Automated evidence cataloguing and metadata extraction

### Proofmode Unpacker
- **Repository**: https://github.com/danielrosehill/Proofmode-Unpacker
- **Description**: Tool for extracting and processing ProofMode evidence packages
- **Use Case**: Working with evidence captured via the ProofMode mobile app

### GuardSpine Spec
- **Repository**: https://github.com/DNYoussef/guardspine-spec
- **Description**: Specification for evidence chain-of-custody tracking
- **Use Case**: Formal specification for evidence handling workflows

## Why Use Evidence Bundling

1. **Integrity verification** - Checksums ensure files haven't been modified
2. **Chain of custody** - Metadata documents who handled evidence and when
3. **Completeness** - Validates that all expected files are present
4. **Portability** - Standard formats work across different tools and platforms
5. **Legal defensibility** - Demonstrates proper evidence handling procedures
