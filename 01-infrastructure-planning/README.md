# Module 01 – Infrastructure Planning

## Overview

This module documents the infrastructure design and resource planning for a Windows Server 2025 homelab running on nested VMware ESXi.

## Lab Objectives

- Design the virtual infrastructure.
- Define hardware and virtualization requirements.
- Plan virtual machine resources.
- Establish an IP addressing scheme.
- Document storage allocation.
- Prepare the environment for Windows Server deployment.

## Lab Environment

| Component | Specification |
|---|---|
| Physical Host | Intel Core i5, 6th–8th Generation |
| Physical Memory | 16 GB RAM |
| Primary Storage | 500 GB SSD |
| Secondary Storage | 1 TB HDD |
| Hypervisor | VMware Workstation |
| Nested Hypervisor | VMware ESXi 8.0.3 |
| Server OS | Windows Server 2025 |
| Network | 192.168.100.0/24 (planned) |
| Active Directory Domain | mylab.local (planned) |

## Planned Virtual Infrastructure

- ESXi nested hypervisor
- Windows Server domain controllers
- Windows Server member server
- Active Directory Domain Services
- DNS and DHCP
- Group Policy
- File Services
- PowerShell administration

## Documentation

- [Hardware Requirements](hardware-requirements.md)
- [VM Resource Allocation](vm-resource-allocation.md)
- [IP Addressing Plan](ip-addressing-plan.md)
- [Storage Design](storage-design.md)

## Implementation Status

**Status:** Planning

The infrastructure will be implemented and validated in subsequent modules.
