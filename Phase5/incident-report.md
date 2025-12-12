# Active Directory Privilege Escalation Incident Report

---

## Executive Summary

An unauthorized privilege escalation attempt was detected within the
corp.local Active Directory environment. A standard domain user account
attempted to obtain elevated privileges through group membership
modification. Security auditing and log correlation enabled rapid
detection and investigation.

---

## Incident Overview

- **Incident Type:** Privilege Escalation Attempt
- **Domain:** corp.local
- **Date Detected:** December 12, 2025
- **Severity:** High

---

## Affected Assets

- **Domain Controller:** DC1
- **Client System:** WIN11-Client1
- **Account Involved:** jdoe

---

## Attack Narrative

The user account `jdoe` authenticated successfully to the domain from
WIN11-Client1. Shortly after authentication, explicit credentials were
used to attempt privileged actions. Group membership changes were
observed targeting privileged Active Directory groups.

---

## Timeline of Events

| Time | Event ID | Description |
|-----|--------|------------|
| T1 | 4624 | Successful user logon |
| T2 | 4648 | Explicit credential usage |
| T3 | 4720 | Domain user account created |
| T4 | 4732 / 4728 | Privileged group modification |
| T5 | 4672 | Special privileges assigned |

---

## Detection & Analysis

Detection was achieved by correlating Windows Security events related to
authentication, credential usage, and group membership changes within a
five-minute time window.

---

## MITRE ATT&CK Mapping

- **T1078:** Valid Accounts
- **T1078.002:** Domain Accounts
- **T1098:** Account Manipulation
- **T1136.002:** Create Account – Domain Account

---

## Containment Actions

- Verified account permissions
- Confirmed no persistent unauthorized access
- Reviewed privileged group memberships

---

## Eradication & Recovery

- No malware identified
- Privileged access verified and secured
- Audit policies confirmed active

---

## Security Recommendations

1. Enforce Just-In-Time (JIT) privileged access
2. Restrict Domain Admin usage to dedicated admin workstations
3. Monitor Event IDs 4720, 4732, 4728 in SIEM
4. Enable alerts for explicit credential usage (4648)
5. Perform regular privileged access reviews

---

## Final Assessment

This incident demonstrates how layered Active Directory auditing,
privileged access baselines, and event correlation enable early
detection of privilege escalation attempts in enterprise environments.

