# Hardware Requirements

## 1. Physical Host Specifications

The physical computer serves as the foundation for the virtualization environment.

| Component               | Specification                     |
| ----------------------- | --------------------------------- |
| Processor               | Intel Core i5, 6th–8th Generation |
| CPU Cores               | 4 physical cores                  |
| Memory                  | 16 GB RAM                         |
| Primary Storage         | 500 GB SSD                        |
| Secondary Storage       | 1 TB HDD                          |
| Host Operating System   | Windows                           |
| Virtualization Platform | VMware Workstation                |

## 2. Virtualization Requirements

The physical host will run VMware Workstation, which will host a nested VMware ESXi 8.0.3 virtual machine.

Requirements:

- Intel VT-x must be enabled in BIOS/UEFI.
- Hardware-assisted virtualization must be exposed to the nested ESXi VM.
- VMware Workstation must support nested virtualization.
- Sufficient memory and storage must be available for guest virtual machines.

## 3. Storage Allocation

| Storage    | Intended Use                                              |
| ---------- | --------------------------------------------------------- |
| 500 GB SSD | Host OS, VMware Workstation, ESXi VM and active guest VMs |
| 1 TB HDD   | ISO files, backups, exports and archived lab files        |

## 4. Memory Considerations

The physical host has 16 GB RAM. Memory allocation must be controlled to avoid excessive resource contention.

The initial ESXi allocation is planned at 8 GB RAM. Running multiple Windows Server guests simultaneously may create memory pressure.

## 5. Limitations

This environment is designed for learning, testing and portfolio demonstration.

It is not intended for production workloads or enterprise performance testing.

## 6. Validation Checklist

- [x] Intel VT-x enabled in BIOS/UEFI
- [x] Virtualization confirmed in Windows Task Manager
- [x] VMware Workstation installed
- [x] Nested virtualization setting available
- [x] SSD and HDD storage verified
