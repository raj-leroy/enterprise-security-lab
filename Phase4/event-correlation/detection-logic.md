# Phase 4 – Detection Logic and Event Correlation

This document defines how privilege escalation activity can be detected
using correlated Windows Security events.

---

## Detection Objective

Detect unauthorized or suspicious attempts to escalate privileges
inside Active Directory.

---

## Key Event IDs Used

| Event ID | Meaning |
|--------|--------|
| 4624 | Successful logon |
| 4648 | Explicit credential use |
| 4672 | Special privileges assigned |
| 4720 | User account created |
| 4732 | Member added to privileged group |
| 4728 | Member added to Domain Admins (alternate) |

---

## Core Detection Logic

### Rule 1 – Suspicious Account Creation
**Trigger:**  
- Event ID 4720

**Why it matters:**  
Creating new domain accounts is rare and high-risk in enterprise environments.

---

### Rule 2 – Privilege Escalation Attempt
**Trigger sequence:**  
1. 4624 – User logs on  
2. 4648 – Explicit credentials used  
3. 4732 or 4728 – Group membership modified

**Why it matters:**  
This sequence strongly indicates an attempt to elevate privileges.

---

### Rule 3 – Privileged Logon Confirmation
**Trigger:**  
- 4672 following a logon event

**Why it matters:**  
Confirms the account received admin-level privileges.

---

## Correlation Window

Time window: **5 minutes**

Events occurring within this window are treated as part of the same incident.

---

## Analyst Decision Points

- Was the user expected to perform admin actions?
- Was the action approved or documented?
- Did the action originate from a workstation or the DC?
- Is this behavior normal for the account?

---

## Outcome

If the above events correlate:
- Raise a **High Severity Alert**
- Begin incident response workflow

