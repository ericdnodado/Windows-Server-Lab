# Virtual Machine Resource Allocation

## 1. Overview

This document defines the initial resource allocation for the nested VMware ESXi environment and its Windows Server virtual machines.

The physical host has 16 GB RAM and a 4-core Intel Core i5 processor. Resource allocation is intentionally conservative to minimize resource contention.

## 2. Nested ESXi Configuration

| Resource | Allocation |
|---|---:|
| vCPU | 2 |
| Memory | 8 GB |
| System Disk | 60 GB |
| Network Adapter | VMXNET3 |
| Firmware | UEFI |
| Nested Virtualization | Enabled |

## 3. Windows Server Virtual Machines

| VM Name | Operating System | vCPU | RAM | Disk |
|---|---|---:|---:|---:|
| DC01 | Windows Server 2025 Core | 1 | 2 GB | 50 GB |
| DC02 | Windows Server 2025 Core | 1 | 2 GB | 50 GB |
| DC03 | Windows Server 2025 Core | 1 | 2 GB | 50 GB |
| MEMBER01 | Windows Server 2025 | 1 | 2 GB | 50 GB |

## 4. Workload Strategy

Because the physical host has only 16 GB RAM:

- Run one or two Windows Server VMs during normal lab exercises.
- Run all three domain controllers only when testing replication or multi-DC scenarios.
- Keep MEMBER01 powered off when it is not required.
- Avoid running additional management VMs simultaneously.
- Monitor memory usage on both the physical host and ESXi.

## 5. Resource Limitations

The 8 GB ESXi allocation leaves approximately 8 GB for the physical Windows host and VMware Workstation, before accounting for overhead.

Running every guest simultaneously may cause memory pressure. The allocations above are initial lab targets, not recommended production specifications.

A physical memory upgrade to 32 GB would provide more room for concurrent workloads.

## 6. Validation Checklist

- [ ] ESXi VM configured with 2 vCPU
- [ ] ESXi VM configured with 8 GB RAM
- [ ] Nested virtualization enabled
- [ ] DC01 resources configured
- [ ] DC02 resources configured
- [ ] DC03 resources configured
- [ ] MEMBER01 resources configured
- [ ] Host and guest memory usage monitored
