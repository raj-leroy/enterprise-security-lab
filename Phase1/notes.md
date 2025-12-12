# Phase 1 — Active Directory Build & Privileged Access Baseline

## Environment
- Host: macOS (VMware Fusion)
- Domain Controller: DC1
- OS: Windows Server 2022
- Domain: corp.local
- Network: Host-only isolated lab

## Key Actions
- Installed AD DS and DNS
- Promoted DC1 as first domain controller
- Configured static IP and self-DNS
- Created dedicated admin account (SecAdmin)
- Disabled built-in Administrator account
- Restricted RDP access to Domain Admins only
- Implemented Tier 0 Privileged Access OU structure

## Security Purpose
This phase establishes a secure baseline for detecting and preventing
privilege escalation inside Active Directory.

