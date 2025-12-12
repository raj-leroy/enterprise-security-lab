Phase 3 – Security Event Evidence

This phase captures Active Directory and logon-related security events.

Evidence:
- dc1_security_phase3.json

Events captured:
- 4732: User added to a privileged group
- 4624: Successful logons
- 4648: Explicit credential usage


Client Evidence (WIN11-Client1)
- win11_security_phase3.json
- User: CORP\jdoe
- Logon Type: Interactive / Kerberos

Events captured:
  - 4624: Successful logon
  - 4648: Explicit credential usage
  - 4625: Access denied attempts

Purpose:
Demonstrates endpoint visibility for domain user activity
and failed privilege escalation attempts.

