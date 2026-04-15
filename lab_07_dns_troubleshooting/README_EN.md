# LAB 7 – DNS Configuration and Troubleshooting

## Description
This lab aims to configure and troubleshoot DNS services within a local network using Cisco Packet Tracer.

DNS records (A and CNAME) were configured, and a failure scenario was simulated to apply troubleshooting techniques and analyze network behavior.

---

## Topology
The network consists of:
- 1 PC (client)
- 1 Cisco 2960 switch
- 1 Server (DNS)

All devices are connected within the same LAN.

---

## DNS Configuration

The following records were configured:

- **A Record**
  - www.test.local → 192.168.1.20

- **CNAME Record**
  - web.test.local → www.test.local

- **Round Robin (concept)**
  - app.test.local → 192.168.1.20
  - app.test.local → 192.168.1.21

---

## Tests Performed

- Domain resolution:
  - ping www.test.local

- CNAME verification:
  - ping web.test.local

- Direct connectivity test:
  - ping 192.168.1.20

---

## Failure Scenario – DNS

- An incorrect DNS address was configured on the PC (192.168.1.99)
- Domain ping failed
- IP ping worked correctly
- The issue was identified as a name resolution problem
- The DNS configuration on the PC was corrected

---

## Analysis

- Network connectivity was working properly
- The issue was related to DNS resolution
- The domain did not resolve correctly due to misconfiguration
- Testing with IP helped rule out network issues

---

## Results

- Understanding of DNS functionality
- Configuration of A and CNAME records
- Identification of DNS failures
- Application of basic troubleshooting techniques
- Validation through connectivity tests

---

## Conclusion

This lab demonstrated how DNS works and how to troubleshoot name resolution issues.

It showed that incorrect DNS configuration can prevent access to services, even when network connectivity is functioning correctly.
