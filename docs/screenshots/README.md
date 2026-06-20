# Screenshots

This folder stores original terminal screenshots used as implementation evidence for the lab documentation.

Screenshots are linked from the relevant phase document instead of being embedded here as a separate gallery.

## Current Evidence

- `phase-1-1-ufw-rules-real.png`: UFW allow rules entered in the lab terminal
- `phase-1-1-ufw-status-real.png`: final UFW status and policies
- `phase-1-1-fail2ban-real.png`: Fail2Ban validation, startup, and SSH jail status
- `phase-1-1-auditd-service-real.png`: auditd enabled and active service status
- `phase-1-1-auditd-rules-real.png`: active audit rules
- `phase-1-2-ca-verification-real.png`: successful OpenSSL verification of the internal CA
- `phase-1-2-csr-real.png`: wildcard CSR creation and subject verification
- `phase-1-2-san-config-real.png`: DNS and IP SAN configuration
- `phase-1-2-chain-verification-real.png`: wildcard certificate trust-chain verification
- `phase-1-2-certificate-details-real.png`: certificate subject, issuer, dates, and SANs
- `phase-1-2-key-match-real.png`: matching certificate and private-key public-key hashes
- `phase-1-3-docker-install-real.png`: Docker Engine installation completed
- `phase-1-3-docker-versions-real.png`: verified Docker runtime component versions
- `phase-1-3-daemon-validation-real.png`: validated Docker daemon hardening configuration
- `phase-1-3-security-options-real.png`: effective Docker security options
- `phase-1-3-userns-mapping-real.png`: dockremap subordinate UID/GID mapping
- `phase-1-3-ciuser-docker-group-real.png`: CI service account Docker group membership
- `phase-1-3-ciuser-ssh-key-real.png`: CI service account Ed25519 key and permissions
- `phase-1-3-ciuser-hello-world-real.png`: successful container run as `ciuser`

## Redaction Rules

For screenshots, I remove or avoid exposing:

- usernames and hostnames where possible
- passwords
- tokens
- private keys
- cloud credentials
- Vault unseal keys
- GitLab initial root passwords or access tokens
