# LAB5 – Analysis of Network Services (DNS, HTTP, FTP)

## Description
This lab analyzes the operation of multiple network services on a single server within a local network using Cisco Packet Tracer.

The following services were configured and analyzed:
- DNS (name resolution)
- HTTP (web access)
- FTP (file transfer)

Simulation Mode was used to observe packet exchange between the client and the server.

---

## Topology
The network consists of:
- 1 PC (client)
- 1 Cisco 2960 switch
- 1 server

All devices are connected within the same Local Area Network (LAN).

---

## Configured Services

| Protocol | Port | Transport |
|---------|------|----------|
| DNS     | 53   | UDP      |
| HTTP    | 80   | TCP      |
| FTP     | 21   | TCP      |

---

## Analysis

The following processes were analyzed:

### DNS
Resolution of the domain `www.test.local` to an IP address.

### HTTP
- Three-way handshake (SYN, SYN-ACK, ACK)
- HTTP request

### FTP
- Authentication (USER / PASS)
- `LIST` command to retrieve files

### Event List
Full communication sequence observed:
DNS → TCP → HTTP

---

## Results

- Successful DNS resolution  
- HTTP connection established  
- Successful FTP authentication  
- File listing retrieved  
- Ports identified  
- Packet flow analyzed in Simulation Mode  

---

## Conclusion

This lab provided an understanding of how application layer protocols (DNS, HTTP, FTP) interact with transport protocols and port usage in client-server communication.
