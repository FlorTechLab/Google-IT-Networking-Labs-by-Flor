# LAB6 – Troubleshooting Network Services (DNS, HTTP, FTP)

## Description
The objective of this laboratory is to identify and troubleshoot failures in different network services within a local network using Cisco Packet Tracer.

DNS, HTTP, and FTP services were configured on the same server. Unlike the previous lab, intentional failures were introduced in order to apply troubleshooting techniques and analyze network behavior using Simulation Mode.

---

## Topology
The network consists of:
- 1 PC (client)
- 1 Cisco 2960 Switch
- 1 Server

All devices are connected within the same local area network (LAN).

---

## Services Analyzed

| Protocol | Port | Transport |
|---------|------|-----------|
| DNS     | 53   | UDP       |
| HTTP    | 80   | TCP       |
| FTP     | 21   | TCP       |

---

## Failure Scenarios

### Scenario 1 – DNS Fail
- Incorrect DNS server configuration on the PC.
- Ping to the IP address worked.
- Ping to the domain failed.
- The DNS address was corrected and the issue was resolved.
- In Simulation Mode, the DNS resolution process was analyzed.

### Scenario 2 – HTTP Fail
- The HTTP service was disabled on the server.
- Network connectivity existed (ping worked) but the web page did not load.
- The HTTP service was enabled and web access was restored.
- In Simulation Mode, the TCP connection and HTTP request were analyzed.

### Scenario 3 – FTP Fail
- The user could log in but could not list files.
- Error: 550 Permission denied.
- The LIST permission was disabled.
- The LIST permission was enabled and the issue was resolved.
- In Simulation Mode, the FTP LIST command and server response were analyzed.

---

## Simulation Mode Analysis
The following processes were analyzed:
- DNS resolution
- TCP connection (Three-way handshake)
- HTTP request
- FTP authentication
- FTP LIST command
- Server error responses

---

## Results

- Identification of DNS, HTTP, and FTP failures
- Network troubleshooting
- Configuration error resolution
- Packet analysis in Simulation Mode
- Troubleshooting methodology

---

## Conclusion

This laboratory helped to understand how to detect and troubleshoot network service failures. Errors can be related to DNS configuration, service status, or user permissions.

Simulation Mode allowed analysis of network traffic and helped to understand how DNS, HTTP, and FTP protocols work during the troubleshooting process.
