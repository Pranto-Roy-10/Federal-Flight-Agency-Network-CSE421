# Federal Flight Agency Network - CSE421

This project was developed for **CSE421: Computer Networks** at **BRAC University**.  
The project focuses on designing and implementing a mission-critical network infrastructure for a fictional **Federal Flight Agency**, a next-generation aerospace organization developing a fully autonomous aircraft fleet.

The network was implemented using **Cisco Packet Tracer** and includes multiple operational units such as:

- Command Center / HQ
- AI Navigation Unit
- Aircraft Simulation Lab
- Maintenance Hangar
- Emergency Control Node

---

## Project Overview

The Federal Flight Agency Network is designed to support secure, reliable, and low-latency communication between critical aerospace systems. The network includes real-time telemetry, AI navigation support, ground command stations, secure service hosting, and emergency backup communication.

The design follows strict segmentation, controlled routing, redundancy, and failover requirements. Default routes were avoided, and specific static and dynamic routing methods were used to control traffic flow.

---

## Major Features

- Complete Cisco Packet Tracer implementation
- VLSM-based IP addressing
- Logical segmentation for each unit and sub-unit
- Static routing and RIPv2 dynamic routing
- Floating static route for backup path
- DHCP server for Simulation Core
- DHCP relay for Testing Sandbox
- Router-based DHCP for AI and Hangar sub-units
- Static addressing for HQ and Emergency Node
- Centralized DNS and Web services hosted in HQ
- SMTP and POP3 email configuration
- Controlled redundancy between AI Unit and HQ
- No default routes used
- End-to-end connectivity validation

---

## Network Units

| Main Unit | Sub-Units |
|---|---|
| Command Center | HQ Control Wing |
| AI Navigation Unit | ML Engine, Data Processing Cell |
| Aircraft Simulation Lab | Simulation Core, Testing Sandbox |
| Maintenance Hangar | Diagnostics Bay, Repair Unit |
| Emergency Control Node | Emergency Node |

---

## Base Network

The base network used for this project is:

```text
10.1.0.0/16
