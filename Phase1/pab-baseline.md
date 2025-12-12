# Privileged Access Baseline (PAB)

## Tier 0 Accounts
- secadmin (Domain Admin)

## Built-in Administrator
- Status: Disabled
- Remains in built-in groups by design (documented exception)

## Privileged Groups
- Domain Admins
- Enterprise Admins

## RDP Access
- Restricted to Domain Admins only

## OU Structure
OU=Privileged Access
 ├─ OU=Tier 0 - Admin Accounts
 └─ OU=Tier 0 - Servers

## Security Rationale
- Reduces attack surface
- Prevents abuse of default admin accounts
- Prepares environment for auditing and detection

