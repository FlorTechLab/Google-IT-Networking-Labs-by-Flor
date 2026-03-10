# LAB4 – Web Session Analysis

**Course:** The Bits and Bytes of Computer Networking (Google)

**Author:** Florencia Horita

**Date:** 10/03/2026

---

## Description

This lab analyzes the complete communication process between a client and a web server within a local network using Cisco Packet Tracer.

A server was configured with DNS and HTTP services to allow the client to access a website using a domain name. Using the **Simulation Mode** in Cisco Packet Tracer, the packets exchanged between devices were observed, allowing analysis of the behavior of the **DNS, TCP, and HTTP** protocols.

---

## Objectives

- Understand the name resolution process using **DNS**.

- Analyze the establishment of a **TCP** connection using the **Three-Way Handshake**.

- Observe the operation of the **HTTP** protocol during a web page request.

- Identify the ports used by each network service.

- Use **Simulation Mode** in Cisco Packet Tracer to inspect network packets.

---

## Network Topology

Simple local network composed of:

- 1 PC (Client)
- 1 Cisco 2960 Switch
- 1 Server (DNS + HTTP)

All devices are connected within the same LAN.

---

## Main Configurations

- **PC0**
  - Configured with an IP address within the local network.
  - DNS server configured for name resolution.

- **Server0**
  - **DNS service enabled**
  - A Record created to resolve `www.test.local`
  - **HTTP service enabled**
  - Main page modified to display the message *Servidor Web Funcionando*

- **Switch 2960**
  - Basic connectivity between network devices.

---

## Observed Process

During the simulation the following communication stages were identified:

1. **ARP Request / Reply**  
   The client obtains the MAC address of the server.

2. **DNS Query / Response**  
   The client queries the DNS server to resolve the domain `www.test.local`.

3. **TCP Three-Way Handshake**
   - SYN
   - SYN-ACK
   - ACK

4. **HTTP Request**  
   The client sends an HTTP request to the server to retrieve the web page.

---

## Results

• Successful domain name resolution using DNS.  

• Correct TCP connection establishment through the Three-Way Handshake.  

• HTTP request successfully sent to the web server.  

• Complete visualization of the communication flow using Simulation Mode.

---

## Included Files

- **LAB4_WEB_SESSION_ANALYSIS_FLOR.pkt** → Cisco Packet Tracer project  
- **LAB4_WEB_SESSION_ANALYSIS_FLOR.pdf** → Technical lab documentation  
- **LAB4_WEB_SESSION_ANALYSIS_FLOR_EN.pdf** → English version of the lab documentation

---

## Notes

This lab demonstrates how **application layer protocols (DNS, HTTP)** and the **transport layer protocol (TCP)** work together to allow access to web services in a network.

The **Simulation Mode** in Cisco Packet Tracer made it possible to observe in detail each packet exchanged during the communication process between the client and the server.
