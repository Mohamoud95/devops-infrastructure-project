# Phase 1.1 - OS Hardening & System Preparation

In this phase, I established the baseline security posture for my Ubuntu lab VM before deploying platform services.

## Completed Controls

### System Updates

I refreshed the package index, upgraded installed packages, and confirmed that no reboot was required.

### Security and Operations Packages

I installed and verified the following security and operations tools:

- UFW
- Fail2Ban
- auditd
- AIDE
- unattended-upgrades
- jq
- yq
- htop
- iotop
- net-tools
- nmap
- python3-pip
- curl
- wget
- git
- ca-certificates
- GnuPG

### Automatic Security Updates

I configured and enabled `unattended-upgrades` to apply security updates automatically.

### UFW Firewall

I reset UFW to a clean state and configured a default-deny inbound posture.

Allowed service ports:

| Port | Purpose |
|---|---|
| 22/tcp | SSH |
| 80/tcp | HTTP / redirect |
| 443/tcp | HTTPS |
| 2222/tcp | GitLab SSH Git operations |
| 5000/tcp | Registry / Harbor HTTPS |
| 6443/tcp | Kubernetes API server |
| 2379:2380/tcp | etcd |
| 10250/tcp | Kubelet API |

I enabled UFW and verified that it was active with the required IPv4 and IPv6 rules.

Original terminal evidence:

![UFW rules added in the lab terminal](screenshots/phase-1-1-ufw-rules-real.png)

![UFW final status in the lab terminal](screenshots/phase-1-1-ufw-status-real.png)

### SSH Hardening

I checked for OpenSSH server and confirmed that it was not installed and nothing was listening on port 22.

I deferred SSH hardening because installing an unused inbound SSH service would add unnecessary attack surface. I will revisit this control if remote SSH access becomes necessary.

### Fail2Ban

I configured Fail2Ban with a local jail configuration and validated it successfully.

Current active jail:

- `sshd`

When I verified the jail, it reported no failed attempts and no banned IPs.

Original terminal evidence:

![Fail2Ban configuration and SSH jail verification in the lab terminal](screenshots/phase-1-1-fail2ban-real.png)

### auditd

I enabled `auditd` and verified that the service was active.

I added audit rules for:

- root command execution
- `/etc/passwd` changes
- `/etc/shadow` changes
- `/etc/sudoers` changes
- `/root/.ssh` changes
- Docker socket access
- Kubernetes configuration changes

I loaded the rules and verified them with `auditctl`.

Original terminal evidence:

![auditd service running in the lab terminal](screenshots/phase-1-1-auditd-service-real.png)

![auditd active rules in the lab terminal](screenshots/phase-1-1-auditd-rules-real.png)

## Evidence Handling

I store original terminal screenshots in `docs/screenshots/` as implementation evidence. Before uploading them, I check that they do not expose passwords, tokens, private keys, cloud credentials, or other sensitive material.
