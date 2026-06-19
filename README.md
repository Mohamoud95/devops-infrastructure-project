# Enterprise DevSecOps Infrastructure Lab

This repository documents a hands-on enterprise DevSecOps infrastructure lab based on a phased build approach.

The lab focuses on building a secure internal platform using Linux hardening, TLS, Docker, GitLab, CI/CD, secrets management, GitOps, monitoring, and Kubernetes.

## Current Progress

- Ubuntu VM baseline setup completed
- Local DNS mappings configured for internal lab services
- Phase 1.1 OS hardening completed
- UFW firewall configured with default-deny inbound rules
- Fail2Ban configured and verified
- auditd enabled with security audit rules
- Phase 1.2 internal TLS certificate setup started
- Docker repository prepared but Docker Engine installation paused until SSL phase is complete

## Lab Environment

| Component | Value |
|---|---|
| Hypervisor | Oracle VirtualBox |
| VM Name | Ubuntu-DevSecOps |
| Hostname | devsecops-lab |
| OS | Ubuntu 26.04 Desktop |
| Network | VirtualBox NAT |
| Internal IP | 10.0.2.15 |

## Internal Service Names

The lab uses local DNS-style names mapped through `/etc/hosts`:

- `gitlab.company.local`
- `registry.company.local`
- `vault.company.local`
- `argocd.company.local`
- `grafana.company.local`
- `k8s.company.local`

## Phase Roadmap

| Phase | Area | Status |
|---|---|---|
| 1.1 | OS Hardening & System Preparation | Complete |
| 1.2 | SSL Certificate Setup | In Progress |
| 1.3 | Docker Engine Installation | Repository Prepared |
| 1.4 | GitLab CE Deployment | Not Started |
| 1.5 | GitLab Runner Installation | Not Started |

## Documentation

- [Phase 1 Overview](docs/phase-1-overview.md)
- [Phase 1.1 OS Hardening](docs/phase-1-1-os-hardening.md)
- [Phase 1.2 SSL Certificate Setup](docs/phase-1-2-ssl-certificate-setup.md)

## Security Notes

This repository is for documenting the project structure and implementation evidence. It should not contain secrets, private keys, passwords, GitLab tokens, Vault unseal keys, API keys, or cloud credentials.
