# Phase 4 – Forensic Indicators and Timeline

This document outlines the forensic artifacts and timeline
used to analyze the privilege escalation attempt.

---

## Primary Evidence Sources

### Domain Controller (DC1)
- Windows Security Event Log
- Active Directory change logs
- Group membership modification events

### Client Workstation (WIN11-Client1)
- Windows Security Event Log
- Logon activity
- Explicit credential usage

---

## Key Forensic Indicators

| Indicator | Description |
|--------|------------|
| User account | jdoe |
| Source host | WIN11-Client1 |
| Target system | DC1 |
| Privileged group | Domain Admins |
| Domain | corp.local |

---

## Event Timeline

### Step 1 – User Logon
- **Event ID:** 4624  
- **Description:** jdoe successfully logged on
- **System:** WIN11-Client1

---

### Step 2 – Explicit Credential Use
- **Event ID:** 4648  
- **Description:** Credentials explicitly used for privileged action
- **System:** DC1

---

### Step 3 – Account Creation (if applicable)
- **Event ID:** 4720  
- **Description:** New domain user account created
- **System:** DC1

---

### Step 4 – Privilege Escalation Attempt
- **Event ID:** 4732 or 4728  
- **Description:** Account added to privileged group
- **System:** DC1

---

### Step 5 – Privileged Token Assignment
- **Event ID:** 4672  
- **Description:** Elevated privileges assigned to account
- **System:** DC1

---

## Analyst Assessment

The sequence of events indicates an attempted or successful
privilege escalation using valid domain credentials.

---

## Confidence Level

**High**

The correlated events occurred within a short time window
and involve direct modification of privileged access.

