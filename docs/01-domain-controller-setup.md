# Domain Controller Build – DC1 (corp.local)

## Purpose of This Phase

This phase builds an enterprise-style Windows Server 2022 domain controller for the `corp.local` domain.  
The goal is to establish a working AD DS + DNS environment that later security monitoring work depends on.

As an IT Security Analyst, understanding how identity, DNS, and authentication infrastructure works is essential for:

- incident investigation  
- authentication failure analysis  
- Kerberos/NTLM log review  
- change control  
- detecting misconfigurations  

This DC setup is the foundation that all later detections and investigations rely on.

---

# 1. Environment Configuration

- **Server Name:** `DC1`
- **OS:** Windows Server 2022  
- **Domain:** `corp.local`
- **Hypervisor:** VMware Fusion
- **Network Mode:** Host-Only (isolated lab network)

### Static IP Addressing

DC1 is configured with:

| Setting | Value |
|--------|--------|
| IP Address | 192.168.50.10 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | (blank – no internet) |
| DNS Server | 127.0.0.1 |

Commands captured:

```powershell
ipconfig /all
Test-Connection 192.168.50.10

