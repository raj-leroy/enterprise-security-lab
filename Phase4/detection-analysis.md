# Phase 4 – Detection Analysis

This section explains the security events generated during Phase 3 and why they are important from a defensive perspective.

---

## Event ID 4624 – Successful Logon

**What happened:**  
A user successfully logged into the domain from a workstation.

**Why this matters:**  
This confirms valid authentication activity and helps establish a baseline of normal user behavior.

**What a defender looks for:**  
- Logon type (interactive vs network)
- Source IP and workstation
- Frequency of logons

---

## Event ID 4648 – Explicit Credentials Used

**What happened:**  
A process attempted to log in using explicitly supplied credentials.

**Why this matters:**  
Attackers commonly use explicit credentials during lateral movement or privilege escalation attempts.

**What a defender looks for:**  
- Which account was used
- Which system initiated the request
- Whether this behavior is expected

---

## Event ID 4672 – Special Privileges Assigned

**What happened:**  
An account was granted elevated privileges during logon.

**Why this matters:**  
This event indicates administrative-level access and is considered high-risk.

**What a defender looks for:**  
- Whether the account should have admin privileges
- Time and frequency of these events
- Correlation with other suspicious activity

---

## Event ID 4732 – User Added to a Group

**What happened:**  
A user was added to a security-enabled group.

**Why this matters:**  
Group membership changes can indicate privilege escalation.

**What a defender looks for:**  
- Which group was modified
- Who performed the action
- Whether the change was authorized

---

## Event Correlation

When these events occur close together, they may indicate an attempted privilege escalation sequence.  
Correlation between workstation logons and domain controller events is critical for detection.

