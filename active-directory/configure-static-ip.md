# Configure Static IP Address on Windows Server 2022

## Overview

This guide demonstrates how to configure a static IPv4 address on a Windows Server 2022 machine before deploying Active Directory Domain Services (AD DS).

A Domain Controller should always use a static IP address to ensure reliable DNS and authentication services.

---

## Lab Environment

| Device | IP Address | Role |
|---|---|---|
| DC1 | 192.168.10.10 | Domain Controller |
| Gateway | 192.168.10.1 | Router |
| DNS | 192.168.10.10 | Local DNS Server |

---

## Objectives

- Configure a static IPv4 address
- Configure DNS settings
- Verify network connectivity
- Prepare the server for AD DS deployment

---

## Network Configuration

| Setting | Value |
|---|---|
| IP Address | 192.168.10.10 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 192.168.10.1 |
| Preferred DNS | 192.168.10.10 |

---

## Steps

### 1. Open Network Connections

- Open **Server Manager**
- Click:
  
```plaintext
Local Server > Ethernet
```

OR

```plaintext
Control Panel > Network and Sharing Center > Change Adapter Settings
```

---

### 2. Open Ethernet Properties

- Right-click the network adapter
- Select:

```plaintext
Properties
```

- Double-click:

```plaintext
Internet Protocol Version 4 (TCP/IPv4)
```

---

### 3. Configure Static IPv4 Address

Select:

```plaintext
Use the following IP address
```

Enter the following configuration:

| Field | Value |
|---|---|
| IP Address | 192.168.10.10 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 192.168.10.1 |
| Preferred DNS Server | 192.168.10.10 |

---

## Validation

### Verify IP Configuration

Open Command Prompt and run:

```powershell
ipconfig
```

Expected result:

```plaintext
IPv4 Address . . . . . . . . . : 192.168.10.10
Subnet Mask  . . . . . . . . . : 255.255.255.0
Default Gateway . . . . . . . : 192.168.10.1
```

---

### Test Network Connectivity

Ping the gateway:

```powershell
ping 192.168.10.1
```

Ping localhost DNS:

```powershell
ping 192.168.10.10
```

---

## Troubleshooting

### No Network Connectivity

- Verify virtual switch configuration
- Check Ethernet adapter status
- Confirm gateway address is correct

---

### Cannot Reach Gateway

- Verify router is powered on
- Check subnet configuration
- Confirm both devices are in the same VLAN/subnet

---

### Incorrect DNS Configuration

A Domain Controller should point to itself for DNS.

Correct:

```plaintext
Preferred DNS: 192.168.10.10
```

Incorrect:

```plaintext
Preferred DNS: 8.8.8.8
```

---

## Skills Practiced

- Windows Server Administration
- IPv4 Configuration
- DNS Configuration
- Enterprise Network Preparation
- Basic Network Troubleshooting

---

## Screenshots

Add screenshots here:

```plaintext
screenshots/static-ip/
```

Example:
- Ethernet properties
- IPv4 configuration
- Successful ping tests
- ipconfig results
