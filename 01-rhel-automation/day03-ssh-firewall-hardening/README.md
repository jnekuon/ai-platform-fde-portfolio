# Week 3, Day 3: SSH Hardening & Firewall Access Control

## Objective
Secure remote administrative access via Ed25519 SSH keys, harden `sshd` configuration on RHEL, and restrict access to an AI inference port (`8000/tcp`) using `firewalld` rich rules.

## Key Commands & Verification
- Generated Ed25519 key pair (`ssh-keygen -t ed25519`) and verified passwordless login.
- Applied drop-in hardening rules in `/etc/ssh/sshd_config.d/99-fde-hardening.conf` (`PermitRootLogin no`, `MaxAuthTries 3`).
- Validated configuration with `sudo sshd -t` before reloading `sshd`.
- Configured `firewalld` rich rule restricting `8000/tcp` to trusted local traffic.
