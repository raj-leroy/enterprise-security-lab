# Phase 3 – Privileged Access & Authentication Auditing

## Objective
Validate that Active Directory audit policies generate security events for:
- User authentication
- Explicit credential usage
- Administrative group membership changes

## Environment
- Domain Controller: DC1 (Windows Server)
- Client: WIN11-Client1
- Domain: corp.local

## Scenario Summary
1. A standard domain user (jdoe) authenticates from a Windows 11 client.
2. An administrative account (secadmin) performs a privileged group modification.
3. Security logs are reviewed to confirm visibility of these actions.

## Key Security Events Observed

### Event ID 4732 – Group Membership Change
- Description: User added to a security-enabled local group
- Actor: CORP\secadmin
- Target: CORP\jdoe
- Group: Remote Desktop Users
- Significance: Confirms administrative access changes are audited

### Event ID 4624 – Successful Logon
- User: CORP\jdoe
- Source Host: WIN11-Client1
- Authentication Type: Kerberos
- Significance: Confirms user authentication activity is logged

### Event ID 4648 – Explicit Credentials Used
- Account Used: CORP\secadmin
- Significance: Confirms credential delegation and administrative actions are visible

## Evidence Files
- event-evidence/dc1_security_phase3.json
- event-evidence/win11_security_phase3.json

