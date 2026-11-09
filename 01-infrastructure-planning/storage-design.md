# Storage Design

## 1. Overview

The lab uses two physical storage devices to separate active virtualization workloads from installation media, backups and archived files.

## 2. Physical Storage

| Storage Device | Capacity | Intended Use |
|---|---:|---|
| SSD | 500 GB | Windows host OS, VMware Workstation, nested ESXi and active VMs |
| HDD | 1 TB | ISO files, VM exports, backups and archived lab data |

## 3. ESXi Datastore Design

The nested ESXi host will use a virtual disk as its primary datastore.

| Component | Planned Configuration |
|---|---|
| Datastore Name | DATASTORE01 |
| Datastore Type | VMFS |
| Virtual Disk | 60 GB |
| Provisioning | Thin (if supported by the selected virtual disk configuration) |
| Purpose | Windows Server virtual machines |

## 4. Virtual Machine Disk Allocation

| Virtual Machine | Virtual Disk |
|---|---:|
| DC01 | 50 GB |
| DC02 | 50 GB |
| DC03 | 50 GB |
| MEMBER01 | 50 GB |

These are initial virtual disk sizes. Actual storage consumption depends on provisioning, guest operating system installation and workload data.

## 5. Backup Strategy

- Store important VM exports and backups on the secondary HDD.
- Keep copies of important configuration files and documentation.
- Do not treat VMware snapshots as backups.
- Verify that backups can be restored before relying on them.

## 6. Storage Best Practices

- Keep sufficient free space on the SSD.
- Monitor datastore utilization.
- Avoid placing all backup copies on the same physical disk as the active VMs.
- Use descriptive names for virtual disks and backup files.
- Document datastore capacity and utilization.

## 7. Validation Checklist

- [ ] SSD capacity verified
- [ ] HDD capacity verified
- [ ] ESXi datastore created
- [ ] Datastore accessible
- [ ] Virtual disk allocation verified
- [ ] Backup storage location identified
- [ ] Free storage capacity monitored
