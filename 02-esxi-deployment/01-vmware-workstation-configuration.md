# VMware Workstation Configuration

## 1. Overview

VMware Workstation is the virtualization platform running on the physical Windows host. It provides the environment required to run VMware ESXi as a nested hypervisor.

## 2. Physical Host Specifications

| Component | Configuration |
|---|---|
| Processor | Intel Core i5 |
| CPU Cores | 4 physical cores |
| Memory | 16 GB RAM |
| Primary Storage | 500 GB SSD |
| Virtualization Platform | VMware Workstation |

## 3. BIOS/UEFI Requirements

Hardware-assisted virtualization must be enabled.

Required setting:

- Intel Virtualization Technology (Intel VT-x)

If supported, Intel VT-d may also be enabled, although it is not the primary requirement for nested virtualization.

## 4. VMware Workstation ESXi VM Settings

| Setting | Planned Value |
|---|---|
| VM Name | ESXI01 |
| Guest OS | VMware ESXi 8 |
| vCPU | 2 |
| Memory | 8 GB |
| Virtual Disk | 60 GB |
| Firmware | UEFI |
| Network Adapter | VMXNET3 |
| Nested Virtualization | Enabled |

## 5. Nested Virtualization

The ESXi virtual machine must be configured to expose hardware-assisted virtualization to its guest operating system.

In VMware Workstation:

1. Power off the ESXi virtual machine.
2. Open VM Settings.
3. Select Processors.
4. Enable **Virtualize Intel VT-x/EPT or AMD-V/RVI** if available.
5. Save the configuration.

## 6. Storage Placement

The ESXi virtual machine and active guest workloads should reside on the SSD to improve performance.

The secondary HDD can store installation media, exports and backup files.

## 7. Validation Checklist

- [ ] Intel VT-x enabled in BIOS/UEFI
- [ ] VMware Workstation detects hardware virtualization
- [ ] ESXI01 configured with 2 vCPU
- [ ] ESXI01 configured with 8 GB RAM
- [ ] 60 GB virtual disk configured
- [ ] Nested virtualization enabled
- [ ] ESXi VM network adapter configured
- [ ] ESXi VM stored on SSD
