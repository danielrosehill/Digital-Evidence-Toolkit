# Anonymisation and Data Obfuscation Tools

Tools for anonymising datasets and obfuscating sensitive information while preserving data utility.

## Database Anonymisation

### Klepto
- **Repository**: https://github.com/hellofresh/klepto
- **Developer**: HelloFresh
- **Description**: Tool for anonymising and sanitising database dumps
- **Features**:
  - Supports PostgreSQL and MySQL
  - Configurable anonymisation rules
  - Can maintain referential integrity
  - Useful for creating safe test datasets from production data

## Use Cases

### Evidence Preparation
When sharing evidence with third parties, you may need to:
- Remove identifying information about witnesses
- Anonymise usernames or account identifiers
- Sanitise metadata that could reveal sources

### Dataset Sharing
For research or legal proceedings where you need to share data:
- Create anonymised versions of databases
- Maintain statistical properties while removing PII
- Ensure compliance with data protection regulations

## Considerations

1. **Reversibility** - Consider whether anonymisation should be reversible (pseudonymisation) or permanent
2. **Data utility** - Balance privacy with the need to maintain meaningful data for analysis
3. **Re-identification risk** - Be aware that combining anonymised datasets can sometimes re-identify individuals
4. **Audit trail** - Document anonymisation processes for legal defensibility
