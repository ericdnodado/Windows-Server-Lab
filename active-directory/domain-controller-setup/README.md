# Active Directory Domain Controller Setup Lab

## Overview

This lab demonstrates the deployment of a Microsoft Active Directory Domain Services (AD DS) environment using Windows Server 2022 and Windows 11 in a virtualized lab setup.

The project focuses on enterprise-style domain controller deployment, DNS configuration, domain joining, validation testing, and troubleshooting.

---

# Objectives

- Install Windows Server 2022
- Configure static IP addressing
- Install Active Directory Domain Services (AD DS)
- Promote server to Domain Controller
- Configure DNS
- Create a new Active Directory forest/domain
- Join Windows 11 client to the domain
- Validate AD functionality
- Perform basic troubleshooting

---

# Environment

| Component | Details |
|---|---|
| Hypervisor | Hyper-V / VMware ESXi / VirtualBox |
| Server OS | Windows Server 2022 |
| Client OS | Windows 11 |
| Domain Name | corp.local |
| DC Hostname | DC1 |
| Client Hostname | CLIENT1 |

---

# Network Topology

```plaintext
+-------------------+
|       DC1         |
| Windows Server    |
| 192.168.101.2     |
| DNS + AD DS       |
+-------------------+
          |
          |
-------------------------
          |
+-------------------+
|     CLIENT1       |
| Windows 11        |
| 192.168.101.11   |
+-------------------+




