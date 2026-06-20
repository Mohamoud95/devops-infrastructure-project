# Phase 1 Overview

In Phase 1, I am building the secure foundation for my DevSecOps lab.

## Objectives

- Prepare and harden the Ubuntu host
- Configure host firewall controls
- Add brute-force protection
- Enable audit logging
- Create internal TLS certificates
- Prepare Docker installation
- Prepare for GitLab and GitLab Runner deployment

## Phase Order

1. OS Hardening & System Preparation
2. SSL Certificate Setup
3. Docker Engine Installation
4. GitLab CE Deployment
5. GitLab Runner Installation

## Current Status

I have completed Phase 1.1 through Phase 1.4. GitLab CE is running with persistent storage, internal TLS, restricted registration, and a validated administrator login. My next step is Phase 1.5 GitLab Runner installation.

I prepared Docker's official repository early, paused installation until the SSL phase was complete, and then installed and hardened Docker Engine in the planned phase sequence.

I deployed GitLab from a pinned container image, mapped persistent data into user-namespace-aware host directories, verified the service health and HTTPS trust chain, and completed the initial application hardening.
