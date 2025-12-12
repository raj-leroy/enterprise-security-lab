# Phase 2 — Advanced Audit Policy Configuration

## Objective
Enable enterprise-grade logging to detect unauthorized privilege escalation
and Active Directory abuse.

## Audit Categories Enabled

### Account Management
- Security Group Management: Success, Failure
- User Account Management: Success, Failure

### Directory Services
- Directory Service Access: Success
- Directory Service Changes: Success

### Privilege Use
- Sensitive Privilege Use: Success, Failure

### Logon / Logoff
- Logon: Success, Failure
- Special Logon: Success

### Policy Change
- Audit Policy Change: Success

## Verification
Audit policies were validated using:
Audit Policy Change: Success


## Security Value
These logs enable detection of:
- Unauthorized Domain Admin membership changes
- Admin account creation
- Privilege escalation attempts
- Audit policy tampering

