# Phase 1.2 - SSL Certificate Setup

This phase creates an internal certificate authority and service certificates for internal lab services.

## Purpose

Internal services such as GitLab, Vault, Argo CD, Grafana, and the container registry should use HTTPS. The lab uses a private internal CA for self-signed internal trust.

## Current Progress

Completed:

- Created PKI directory structure under `/etc/ssl/company/`
- Secured private key directory permissions
- Generated internal CA private key
- Generated internal CA certificate
- Installed the internal CA into the Ubuntu trust store

In progress:

- Verify internal CA certificate
- Generate wildcard service certificate for `*.company.local`

## PKI Directory Structure

| Path | Purpose |
|---|---|
| `/etc/ssl/company/ca` | Internal CA key and certificate |
| `/etc/ssl/company/certs` | Issued certificates |
| `/etc/ssl/company/private` | Private keys |
| `/etc/ssl/company/csr` | Certificate signing requests |

The private key directory was secured with owner-only access.

## Internal CA

The internal CA is used to sign certificates for lab services. The CA certificate has been added to the local trust store so the VM can trust certificates issued by this CA.

## Safety Notes

Do not commit private keys, CA keys, passwords, or generated secret material to GitHub.

Files that must stay out of GitHub include:

- `*.key`
- `*.key.pem`
- private CA material
- tokens
- passwords
- cloud credentials
