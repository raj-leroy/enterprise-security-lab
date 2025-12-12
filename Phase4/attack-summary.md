# Phase 4 – Attack Simulation Summary

This section summarizes the simulated privilege escalation attempts performed during Phase 3.

---

## Attacker Profile

- **Account:** jdoe
- **Role:** Standard domain user
- **Source System:** WIN11-Client1
- **Target System:** DC1 (Domain Controller)

---

## Attack Attempt 1 – Unauthorized Privilege Escalation

**Description:**  
The user attempted to add their account to a privileged group.

**Result:**  
The action was denied due to insufficient privileges.

**Evidence Generated:**  
- Event ID 4624 (successful logon)
- Event ID 4648 (explicit credentials)
- No successful group modification event occurred

---

## Attack Attempt 2 – Privileged Group Modification by Admin

**Description:**  
A privileged account added the user to a built-in security group.

**Result:**  
The action succeeded and modified group membership.

**Evidence Generated:**  
- Event ID 4732 (user added to group)
- Event ID 4672 (special privileges assigned)

---

## Key Observation

Unauthorized privilege escalation attempts failed, but authorized privileged actions were logged and detectable.  
This confirms auditing and logging controls are functioning correctly.

