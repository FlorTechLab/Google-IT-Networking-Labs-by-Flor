# LAB – Wireless Network Design with DHCP

## 🎯 Objective
Design and implement a distributed wireless network using multiple Access Points, applying DHCP for automatic IP address assignment and improving coverage through Wi-Fi channel planning.

---

## 🧩 Description
This lab simulates a network environment in a multi-floor building where stable wireless connectivity is required.

A network is implemented using multiple Access Points with the same SSID and different channels to avoid interference, along with a router acting as both gateway and DHCP server.

---

## 🌐 Topology
- 4 PCs (PC1, PC2, PC3, PC4)  
- 1 Switch  
- 1 Router  
- 4 Access Points (AP1, AP2, AP3, AP4)

**Network flow:**

PCs → Access Points → Switch → Router  

---

## 📡 Access Point Configuration
- SSID: Empresa_WIFI  
- Security: WPA2-PSK  
- Password: Empresa123  

**Channels:**
- AP1 → Channel 1  
- AP2 → Channel 6  
- AP3 → Channel 11  
- AP4 → Channel 1  

---

## 🌍 Router Configuration
- IP: 192.168.1.1  
- Subnet Mask: 255.255.255.0  

---

## 🧠 DHCP (Router)

```bash
ip dhcp excluded-address 192.168.1.1
ip dhcp pool LAN
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 8.8.8.8

```
---

## 💻 PCs

Configured in automatic DHCP mode.

🔍 Tests
ping 192.168.1.1

✔ Result: successful connectivity
✔ Automatic IP assignment confirmed

---

## 📊 Analysis
PCs connect to the nearest Access Point
The switch centralizes traffic
The router acts as gateway and DHCP server
Full network connectivity is validated

---

## 🧪 Results
Functional wireless network
DHCP operational
Channel distribution without interference
Communication between all devices

___

## 🧠 Conclusion

This lab helped understand the design of wireless networks using multiple Access Points, highlighting the importance of channel planning and the use of DHCP for automating network configuration.

The router plays a key role as both gateway and IP address assignment server.

---

## ⚠️ Simulation considerations
Roaming between Access Points is not fully realistic
AP selection is not always signal-based
Signal strength does not fully affect connectivity
