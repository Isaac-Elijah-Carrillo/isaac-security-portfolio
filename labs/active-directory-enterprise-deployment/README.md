# Enterprise Active Directory Deployment & Domain Integration Lab

## Overview

In this lab, I built an enterprise-style Active Directory environment using Oracle VirtualBox. The lab simulates a basic corporate network by deploying a Windows Server 2022 Domain Controller, configuring Active Directory Domain Services (AD DS) and DNS, and joining a Windows 11 workstation to the domain.

This project demonstrates core Windows Server administration, identity and access management, enterprise networking, and Active Directory fundamentals commonly used in Help Desk, Systems Administration, and SOC environments.

---

## Objectives

- Deploy Windows Server 2022 as a Domain Controller
- Configure Active Directory Domain Services (AD DS)
- Configure Active Directory Integrated DNS
- Create a new Active Directory forest (`corp.local`)
- Configure an isolated VirtualBox network
- Deploy a Windows 11 Enterprise workstation
- Configure static IP addressing
- Join a Windows workstation to the Active Directory domain
- Verify domain authentication and DNS functionality

---

## Lab Environment

| Component | Technology |
|-----------|------------|
| Hypervisor | Oracle VirtualBox |
| Server OS | Windows Server 2022 |
| Client OS | Windows 11 Pro |
| Active Directory | Active Directory Domain Services (AD DS) |
| DNS | Active Directory Integrated DNS |
| Domain | corp.local |
| Network | VirtualBox NAT Network (AD_LAB) |

---

## Network Topology

```text
                    AD_LAB
              192.168.100.0/24
    -------------------------------------

           DC01
    Windows Server 2022
    Active Directory
    DNS Server

      IP: 192.168.100.10
             │
             │
      Kerberos / DNS
             │
             │
      CLIENT01
     Windows 11 Pro

      IP: 192.168.100.20
```

---

## Technologies Used

- Windows Server 2022
- Windows 11 Pro
- Oracle VirtualBox
- Active Directory Domain Services
- Active Directory Users and Computers
- DNS
- TCP/IP
- Kerberos
- Windows Server Manager

---

## Skills Demonstrated

- Active Directory Administration
- Windows Server Administration
- DNS Configuration
- Static IP Configuration
- Enterprise Identity Management
- Domain Controller Deployment
- Domain Join Operations
- Virtual Machine Administration
- Network Troubleshooting
- Authentication Validation

---

## Implementation Summary

### Phase 1 — Virtual Infrastructure

- Created an isolated VirtualBox NAT Network
- Provisioned a Windows Server 2022 virtual machine (DC01)
- Provisioned a Windows 11 Pro virtual machine (CLIENT01)

---

### Phase 2 — Domain Controller Configuration

- Assigned a static IP address to DC01
- Installed Active Directory Domain Services
- Installed DNS Server
- Promoted the server to a Domain Controller
- Created a new Active Directory forest:

```
corp.local
```

---

### Phase 3 — Client Deployment

- Installed Windows 11 Pro
- Configured static IPv4 addressing
- Configured DNS to use the Domain Controller
- Verified connectivity with ICMP
- Verified DNS name resolution

---

### Phase 4 — Domain Integration

- Joined CLIENT01 to the `corp.local` domain
- Authenticated using the domain administrator account
- Verified domain authentication
- Verified the computer object was created within Active Directory

---

## Validation

### Network Connectivity

Validated communication between CLIENT01 and DC01.

```cmd
ping 192.168.100.10
```

---

### DNS Resolution

Validated Active Directory DNS functionality.

```cmd
nslookup corp.local
```

---

### Authentication

Verified successful domain authentication.

```cmd
whoami

echo %logonserver%
```

Expected output:

```text
corp\Administrator

\\DC01
```

---

### Active Directory Verification

Verified the workstation appears inside Active Directory Users and Computers.

```
corp.local
    └── Computers
            └── CLIENT01
```

---

## Screenshots

### Screenshot #1 — Enterprise Lab Overview

*Both virtual machines running after successful domain integration.*

![Windows AD Lab 1 Screenshot #1](screenshots/Windows%20AD%20Lab%201%20Screenshot%20%231.png)

---

### Screenshot #2 — Active Directory Verification

*CLIENT01 successfully joined to Active Directory.*

![Windows AD Lab 1 Screenshot #2](screenshots/Windows%20AD%20Lab%201%20Screenshot%20%232.png)

---

### Screenshot #3 — Network & DNS Validation

*Validated connectivity and Active Directory DNS functionality.*

![Windows AD Lab 1 Screenshot #3](screenshots/Windows%20AD%20Lab%201%20Screenshot%20%233.png)

---

### Screenshot #4 — Domain Membership

*CLIENT01 successfully joined to the `corp.local` domain.*

![Windows AD Lab 1 Screenshot #4](screenshots/Windows%20AD%20Lab%201%20Screenshot%20%234.png)

---

### Screenshot #5 — Server Roles

*Windows Server configured with Active Directory Domain Services and DNS.*

![Windows AD Lab 1 Screenshot #5](screenshots/Windows%20AD%20Lab%201%20Screenshot%20%235.png)

---

## Key Takeaways

This lab provided hands-on experience deploying and administering a basic enterprise Active Directory environment. Beyond installing Windows Server, the project required configuring identity services, DNS, virtual networking, workstation deployment, and validating successful domain authentication between systems.

The completed environment serves as the foundation for future enterprise labs involving Group Policy, Organizational Units, Windows Event Logging, Sysmon, Splunk integration, and Active Directory security monitoring.

---

## Future Improvements

- Create Organizational Units (OUs)
- Create enterprise users and security groups
- Configure Group Policy Objects (GPOs)
- Deploy Sysmon
- Forward Windows Event Logs to Splunk
- Perform Active Directory attack simulations
- Build Blue Team detection use cases
