# DNS Troubleshooting Lab

## Overview

This lab demonstrates basic network troubleshooting techniques using Cisco Packet Tracer.

The environment includes a client PC, a router configured as a DHCP server, and a DNS/Web server. The lab focuses on validating IP connectivity, DNS resolution, and troubleshooting DNS-related issues using common networking tools.

---

## Objectives

- Configure DHCP on a router
- Configure DNS and HTTP services on a server
- Verify network connectivity using ICMP
- Test DNS name resolution
- Simulate and troubleshoot DNS failures
- Analyze network behavior using diagnostic tools

---

## Technologies Used

- Cisco Packet Tracer
- DHCP
- DNS
- ICMP
- IPv4
- HTTP
- ping
- nslookup
- tracert

---

## Network Topology

```text
PC1 → SW1 → R1 → Server1
```
<img width="1126" height="720" alt="image" src="https://github.com/user-attachments/assets/e9e0982c-5929-44fb-a762-3958225abe74" />


### Devices

| Device | Role |
|---|---|
| PC1 | Client device |
| SW1 | Layer 2 switch |
| R1 | Router / DHCP Server |
| Server1 | DNS and HTTP Server |

---

## IP Addressing Scheme

| Device | IP Address |
|---|---|
| R1 | 192.168.10.1 |
| Server1 | 192.168.10.10 |
| PC1 | DHCP Assigned |

---

## Router Configuration

### Interface Configuration

```bash
enable
configure terminal

interface g0/0
ip address 192.168.10.1 255.255.255.0
no shutdown
exit
```

### DHCP Configuration

```bash
ip dhcp excluded-address 192.168.10.1

ip dhcp pool LAN
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1
dns-server 192.168.10.10
```

---

## Server Configuration

### Static IP Configuration

| Setting | Value |
|---|---|
| IP Address | 192.168.10.10 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 192.168.10.1 |
| DNS Server | 192.168.10.10 |

### Enabled Services

- DNS
- HTTP

### DNS Record

| Domain | IP Address |
|---|---|
| empresa.com | 192.168.10.10 |

---

## Client Configuration

PC1 was configured in DHCP mode to automatically receive:

- IP address
- Subnet mask
- Default gateway
- DNS server

### Verification Command

```bash
ipconfig
```

---

## Connectivity Tests

### ICMP Connectivity Test

```bash
ping 192.168.10.10
```

### DNS Resolution Test

```bash
nslookup empresa.com
```

### Connectivity Using Domain Name

```bash
ping empresa.com
```

### Route Tracing

```bash
tracert empresa.com
```

---

## DNS Failure Simulation

A DNS issue was simulated by manually configuring an incorrect DNS server on the client PC.

### Incorrect DNS Example

```text
1.1.1.1
```

### Result

```bash
nslookup empresa.com
```

Result:
- DNS request timed out
- Name resolution failed

However:

```bash
ping 192.168.10.10
```

continued to work successfully.

This demonstrates the difference between:
- IP connectivity issues
- DNS resolution issues

---

## Troubleshooting Process

### Problem

The client was unable to access internal resources using domain names.

### Root Cause

Incorrect DNS server configuration.

### Solution

The DNS configuration was restored to:

```text
192.168.10.10
```

After correcting the DNS settings:

```bash
nslookup empresa.com
ping empresa.com
```

worked successfully again.

---

## Key Concepts Learned

- DHCP automatic addressing
- DNS name resolution
- ICMP connectivity testing
- Network troubleshooting methodology
- Difference between connectivity and DNS issues
- Basic route tracing

---

## Skills Demonstrated

- Router configuration
- DHCP deployment
- DNS server configuration
- Network diagnostics
- Troubleshooting techniques
- Cisco Packet Tracer topology implementation

---

## Project Files

```text
dns-troubleshooting-lab/
│
├── README_EN.md
├── README_ES.md
│
├── dns-troubleshooting-lab_EN.pdf
├── dns-troubleshooting-lab_ES.pdf
│
├── dns-troubleshooting-lab.pkt
│
└── images/
```

---

## Notes

Cisco Packet Tracer has some limitations compared to real-world environments.

Some advanced tools and networking behaviors may differ from actual operating systems and enterprise networks. However, the simulator provides an excellent environment for learning networking fundamentals and troubleshooting concepts.
