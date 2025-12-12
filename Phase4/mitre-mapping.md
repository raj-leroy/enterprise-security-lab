# Phase 4 – MITRE ATT&CK Mapping

This section maps the Phase 3 activity to MITRE ATT&CK techniques.

---

## Technique Mapping

### T1078 – Valid Accounts
**Why it applies:**  
A legitimate domain user account (jdoe) was used to authenticate and access resources.

**Evidence:**  
- Windows Security Event ID 4624 (successful logon)

---

### T1078.002 – Valid Accounts: Domain Accounts (optional detail)
**Why it applies:**  
The account used is a domain account, not a local-only account.

**Evidence:**  
- Windows Security Event ID 4624 showing CORP.LOCAL domain context

---

### T1136.002 – Create Account: Domain Account (only include if you created a new domain user)
**Why it applies:**  
A new domain user account was created in Active Directory.

**Evidence:**  
- Windows Security Event ID 4720 (user account created)

**Note:**  
Remove this section if you did not create a new domain user during the simulation.

---

### T1098 – Account Manipulation
**Why it applies:**  
Group membership for an account was modified to change access/privileges.

**Evidence:**  
- Windows Security Event ID 4732 (member added to a security-enabled local group)

---

### T1078 + T1098 Combined Behavior
**Why it matters:**  
Valid credentials + account privilege changes is a common real-world escalation path.

**Evidence:**  
- 4624 (logon)
- 4732 (group membership change)

---

## Defender Takeaways

- Successful logons prove account usage (4624).
- Explicit credential use is a strong signal for lateral movement / misuse (4648).
- Group membership change is the clearest privilege escalation indicator (4732).
- Privileged logons are corroborated by elevated privilege assignment (4672).

