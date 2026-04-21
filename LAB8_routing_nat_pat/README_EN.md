# IT-Network-Labs-Flor-8

# LAB 8 – Routing, NAT and PAT Configuration  
**Course:** The Bits and Bytes of Computer Networking (Google)  

**Author:** Florencia Horita  

**Date:** 04/20/2026  

---

## Description  
This lab demonstrates how to configure communication between a private network and an external network using **static routing**, **NAT**, and **PAT**.  

It simulates a real-world scenario where a host from a private network accesses an external server, similar to Internet access.  

---

## Objectives  
- Understand how routing works between networks.  
- Configure static routes on Cisco routers.  
- Implement NAT (Network Address Translation).  
- Implement PAT (Port Address Translation).  
- Verify connectivity between private and external networks.  

---

## Topology  
[PC] → [R1] → [R2] → [Server]  

---

## Network Configuration  

### PC  
- **IP:** 10.0.0.2  
- **Subnet Mask:** 255.255.255.0  
- **Gateway:** 10.0.0.1  

### Server  
- **IP:** 8.8.8.8  
- **Subnet Mask:** 255.255.255.0  
- **Gateway:** 8.8.8.1  

### Addressing Table  

| Device | Interface | IP |
|--------|----------|------|
| PC | — | 10.0.0.2 |
| R1 | G0/0 | 10.0.0.1 |
| R1 | G0/1 | 200.1.1.1 |
| R2 | G0/0 | 200.1.1.2 |
| R2 | G0/1 | 8.8.8.1 |
| Server | — | 8.8.8.8 |

---

## Router Configuration  

### Router R1  
```bash
interface g0/0
ip address 10.0.0.1 255.255.255.0
no shutdown

interface g0/1
ip address 200.1.1.1 255.255.255.0
no shutdown
```

### Router R2  
```bash
interface g0/0
ip address 200.1.1.2 255.255.255.0
no shutdown

interface g0/1
ip address 8.8.8.1 255.255.255.0
no shutdown
```

---

## Routing Configuration  

### Default Route on R1  
```bash
ip route 0.0.0.0 0.0.0.0 200.1.1.2
```

### Return Route on R2  
```bash
ip route 10.0.0.0 255.255.255.0 200.1.1.1
```

---

## NAT and PAT Configuration (R1)  

### Access List  
```bash
access-list 1 permit 10.0.0.0 0.0.0.255
```

### NAT Interfaces  
```bash
interface g0/0
ip nat inside

interface g0/1
ip nat outside
```

### Enable PAT  
```bash
ip nat inside source list 1 interface g0/1 overload
```

---

## Verification  

### Connectivity Test  
```bash
ping 8.8.8.8
```

### NAT Verification  
```bash
show ip nat translations
```

---

## Results  
- Successful communication between the PC and the server.  
- Correct translation from private IP to public IP.  
- PAT allows multiple connections using a single public IP.  

---

## Analysis  
The network flow was as follows:  

- The PC sends traffic to the server.  
- R1 translates the private IP using NAT/PAT.  
- R2 routes the traffic to the server.  
- The server responds successfully.  
