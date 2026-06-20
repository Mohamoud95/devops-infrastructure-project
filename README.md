# Enterprise DevSecOps Infrastructure Lab

I am building this enterprise DevSecOps infrastructure lab using a phased, security-first approach.

My goal is to build and document a secure internal platform using Linux hardening, TLS, Docker, GitLab, CI/CD, secrets management, GitOps, monitoring, and Kubernetes.

## Current Progress

- I completed the Ubuntu VM baseline setup.
- I configured local DNS mappings for the internal lab services.
- I completed Phase 1.1 OS hardening.
- I configured UFW with a default-deny inbound policy.
- I configured and verified Fail2Ban.
- I enabled auditd and loaded security audit rules.
- I completed Phase 1.2 internal TLS certificate setup.
- I prepared Docker's official repository and will install Docker Engine in Phase 1.3.

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

I mapped these internal service names through `/etc/hosts`:

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
| 1.2 | SSL Certificate Setup | Complete |
| 1.3 | Docker Engine Installation | Repository Prepared |
| 1.4 | GitLab CE Deployment | Not Started |
| 1.5 | GitLab Runner Installation | Not Started |

## Documentation

- [Phase 1 Overview](docs/phase-1-overview.md)
- [Phase 1.1 OS Hardening](docs/phase-1-1-os-hardening.md)
- [Phase 1.2 SSL Certificate Setup](docs/phase-1-2-ssl-certificate-setup.md)

## Security Notes

I use this repository to document the project structure, security decisions, progress, and original terminal evidence. I do not commit secrets, private keys, passwords, GitLab tokens, Vault unseal keys, API keys, or cloud credentials.
