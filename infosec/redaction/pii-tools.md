# PII Detection and Redaction Tools

Tools for detecting and redacting Personally Identifiable Information (PII) from documents, images, and data.

## Detection Tools

### Octopii
- **Repository**: https://github.com/redhuntlabs/Octopii
- **Description**: AI-powered PII scanner that can detect sensitive information in images, documents, and databases
- **Features**:
  - Uses machine learning for detection
  - Supports multiple file formats
  - Can scan images for visible PII

### pdscan
- **Repository**: https://github.com/ankane/pdscan
- **Description**: Scans your data stores for unencrypted personal data (PII)
- **Supports**: PostgreSQL, MySQL, S3, and local files
- **Use Case**: Finding PII that needs encryption or redaction

### Hawk-Eye
- **Repository**: https://github.com/rohitcoder/hawk-eye
- **Description**: Privacy-focused scanner for finding PII and sensitive data in codebases and documents
- **Use Case**: Pre-release scanning, compliance checks

## Redaction/Masking Tools

### PII Masker
- **Repository**: https://github.com/HydroXai/pii-masker
- **Description**: Tool for masking PII in text data
- **Features**:
  - Multiple masking strategies
  - Configurable entity types

### A5-PII-Anonymizer
- **Repository**: https://github.com/AgenticA5/A5-PII-Anonymizer
- **Description**: Automated PII anonymization tool
- **Features**:
  - Named entity recognition
  - Configurable replacement strategies

### pII-guard
- **Repository**: https://github.com/rpgeeganage/pII-guard
- **Description**: PII detection and protection utility
- **Use Case**: Runtime PII filtering and logging protection

## Best Practices

1. **Scan before sharing** - Always run PII detection on evidence before distributing
2. **Multiple passes** - Use more than one tool as each has different detection capabilities
3. **Manual review** - Automated tools may miss context-dependent PII
4. **Document redactions** - Keep records of what was redacted and why for audit purposes
