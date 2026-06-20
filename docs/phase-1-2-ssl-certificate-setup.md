# Phase 1.2 - SSL Certificate Setup

In this phase, I created an internal certificate authority and a wildcard service certificate for my internal lab services.

## Purpose

I configured private internal trust so GitLab, Vault, Argo CD, Grafana, and the container registry can use HTTPS without relying on a public certificate authority.

## Status

I have completed Phase 1.2.

Completed work:

- I created the PKI directory structure under `/etc/ssl/company/`.
- I secured the private key directory permissions.
- I generated the internal CA private key and certificate.
- I installed the internal CA into the Ubuntu trust store.
- I verified the internal CA certificate with OpenSSL.
- I generated a 4096-bit wildcard service private key.
- I created and verified the wildcard certificate signing request.
- I defined the required DNS and IP Subject Alternative Names.
- I signed the wildcard certificate with the internal CA.
- I verified the trust chain, identity, issuer, validity dates, and SANs.
- I confirmed that the wildcard certificate matches its private key.

## PKI Directory Structure

| Path | Purpose |
|---|---|
| `/etc/ssl/company/ca` | Internal CA key and certificate |
| `/etc/ssl/company/certs` | Issued certificates |
| `/etc/ssl/company/private` | Private keys |
| `/etc/ssl/company/csr` | Certificate signing requests |

I secured the private key directory with owner-only access.

## Internal CA

I use the internal CA to sign certificates for lab services. I added its certificate to the local trust store so the VM trusts certificates issued by this CA.

Original terminal evidence:

![Internal CA certificate verification in the lab terminal](screenshots/phase-1-2-ca-verification-real.png)

## Wildcard Certificate

I issued the wildcard certificate for `*.company.local` and included explicit DNS and IP SAN entries for internal services and local testing endpoints.

### Certificate Signing Request

Original terminal evidence:

![Wildcard CSR creation and subject verification](screenshots/phase-1-2-csr-real.png)

### Subject Alternative Names

Original terminal evidence:

![Wildcard certificate SAN configuration](screenshots/phase-1-2-san-config-real.png)

### Trust Chain Verification

Original terminal evidence:

![Wildcard certificate trust-chain verification](screenshots/phase-1-2-chain-verification-real.png)

### Certificate Identity And Validity

Original terminal evidence:

![Wildcard certificate subject issuer dates and SANs](screenshots/phase-1-2-certificate-details-real.png)

### Private Key Match

I extracted and hashed the public keys from both the private key and certificate. Their SHA-256 hashes matched exactly.

Original terminal evidence:

![Wildcard certificate and private-key match](screenshots/phase-1-2-key-match-real.png)

## Validation Notes

OpenSSL validation caught a case-sensitive extension-name typo and a malformed IP SAN before issuance. I corrected both before signing the certificate, which demonstrated the value of validating certificate profiles before deployment.

## Safety Notes

I do not commit private keys, CA keys, passwords, or generated secret material to GitHub.

Files that must stay out of GitHub include:

- `*.key`
- `*.key.pem`
- private CA material
- tokens
- passwords
- cloud credentials
