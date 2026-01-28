# Device Security for Evidence Handling

## Overview

Proper device security ensures your evidence remains protected from unauthorized access, tampering, or loss.

## Basic Security Measures

### Full Disk Encryption

**Why:** Protects evidence if device is lost or stolen.

**Windows:**
- BitLocker (Pro/Enterprise) or VeraCrypt

**macOS:**
- FileVault (built-in)

**Linux:**
- LUKS encryption (usually configured at install)

### Strong Authentication

- Use strong, unique passwords for devices
- Enable biometric + PIN/password combination
- Set short auto-lock timeout (1-2 minutes)
- Disable password hints

### Software Updates

- Keep OS and applications updated
- Enable automatic security updates
- Update evidence-related tools regularly

## Evidence Storage Security

### Separate Storage
- Use dedicated encrypted drive/partition for evidence
- Consider hardware-encrypted external drives
- VeraCrypt containers for sensitive evidence

### Access Control
- Limit who can access evidence storage
- Log access when possible
- Use principle of least privilege

## Mobile Device Security

### For Evidence Capture Devices
- Device encryption enabled
- Strong PIN (6+ digits)
- Biometric disabled for high-security scenarios
- Disable lock screen notifications
- Auto-upload to secure cloud configured

### Apps to Consider
- **Shelter** (Android) - Work profile isolation
- **App lockers** - Additional layer for evidence apps

## Network Security

- Use secure networks for evidence transfer
- VPN when on untrusted networks
- Verify HTTPS for cloud services
- Avoid public WiFi for evidence uploads

## Backup Security

- Encrypt backups
- Test restore procedures
- Store backup keys separately from backups
- Multiple backup locations (local + cloud)

## Physical Security

- Don't leave devices unattended
- Use privacy screens in public
- Secure home/office storage
- Consider tamper-evident bags for chain of custody

## Incident Response

If device is compromised:
1. Document the incident
2. Preserve evidence of the compromise
3. Assess what evidence may be affected
4. Consider legal/professional consultation
5. Review and improve security measures
