# LAB 9 – NAT, Routing and ACL Troubleshooting

## Objective
Diagnose and resolve connectivity issues in a network using static routing, NAT, PAT, and Access Control Lists (ACL), applying a structured troubleshooting approach.

---

## Description
This lab simulates a real-world environment where multiple configuration errors prevent communication between a private network and an external server.

The focus is on identifying the root cause and applying the necessary fixes to restore connectivity.

---

## Topology
The network consists of:

- 2 PCs (PC1 and PC2)
- 1 Switch
- 2 Routers (R1 and R2)
- 1 Server

Connectivity:

PC1 / PC2 → Switch → R1 → R2 → Server

---

## Network Configuration

### PCs
- PC1 → 192.168.1.10 / GW 192.168.1.1
- PC2 → 192.168.1.20 / GW 192.168.1.1

### Server
- IP → 200.0.0.2
- Gateway → 200.0.0.1

---

## Routing

- R1:
  - ip route 200.0.0.0 255.255.255.0 10.0.0.2

- R2:
  - ip route 192.168.1.0 255.255.255.0 10.0.0.1

---

## NAT / PAT Configuration (R1)

### ACL
- access-list 1 permit 192.168.1.0 0.0.0.255

### Interfaces
- g0/0 → ip nat inside
- g0/1 → ip nat outside

### PAT
- ip nat inside source list 1 interface g0/1 overload

---

## Tests Performed

- Server connectivity test  
- NAT verification (`show ip nat translations`)  
- Routing verification (`show ip route`)  
- ACL verification (`show access-lists`)  
- Interface verification (`show ip interface brief`)  

---

## Failure Scenario

- Ping to the server failed  
- No NAT translations were observed  
- Traffic could not leave the router  
- Missing static routes were detected  

---

## Resolution

The following corrections were applied:

- Fixed subnet mask on router link (/30)  
- Added missing static routes in R1 and R2  
- Verified NAT configuration (inside/outside)  
- Validated ACL  
- Checked interface status  

---

## Final Verification

- Successful ping to the server (with initial packet loss)  
- Active NAT translations  
- End-to-end connectivity restored  

---

## Analysis

The main issue was related to routing, which prevented traffic from leaving the router.

As a result, NAT was not applied because there was no outbound traffic to translate.

Once routing was corrected, full communication was restored and NAT began working correctly.

---

## Skills Applied

- Network troubleshooting  
- NAT and PAT configuration  
- Routing analysis  
- Cisco command interpretation  
- Connectivity issue diagnosis  

---

## Results

- Understanding of network traffic flow  
- Identification of routing issues  
- Validation of NAT/PAT functionality  
- Practical troubleshooting experience  

---

## Conclusion

This lab demonstrates troubleshooting techniques in a realistic environment, identifying and resolving routing and configuration issues that prevented connectivity.

Key skills such as diagnosis, analysis, and network validation were reinforced.
