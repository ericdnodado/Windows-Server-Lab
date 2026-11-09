# IP Addressing Plan

## 1. Network Overview

The lab uses an IPv4 subnet for the nested ESXi environment and Windows Server infrastructure.

| Parameter | Configuration |
|---|---|
| Network Address | 192.168.100.0/24 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | To be confirmed |
| DNS Domain | mylab.local |
| Address Assignment | Static IP for infrastructure servers |

## 2. IP Address Allocation

| Device | Hostname | IP Address |
|---|---|---|
| ESXi Host | ESXI01 | 192.168.100.100 |
| Domain Controller 1 | DC01 | 192.168.100.20 |
| Domain Controller 2 | DC02 | 192.168.100.21 |
| Domain Controller 3 | DC03 | 192.168.100.22 |
| Member Server | MEMBER01 | 192.168.100.30 |

## 3. Addressing Guidelines

- Infrastructure servers will use static IPv4 addresses.
- Domain controllers will use internal DNS servers.
- The default gateway must match the actual lab network configuration.
- IP addresses must not conflict with existing devices or DHCP assignments.
- DNS configuration will be documented in the DNS module.

## 4. Network Considerations

- Verify the physical LAN subnet and VMware virtual network configuration.
- Confirm that all planned addresses are reachable within the intended lab network.
- Avoid duplicate IP addresses.
- Document any NAT or isolated virtual network configuration.

## 5. Validation Checklist

- [x] ESXi management IP documented
- [ ] Confirm physical LAN subnet
- [ ] Confirm default gateway
- [ ] Check VMware virtual network configuration
- [ ] Check DHCP address pool
- [ ] Verify no duplicate IP addresses
- [ ] Confirm static IP assignments
