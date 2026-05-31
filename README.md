# Federal Flight Agency Network - CSE421

This project was developed for **CSE421: Computer Networks** at **BRAC University**.
The project focuses on designing and implementing a mission-critical network infrastructure for a fictional **Federal Flight Agency**, a next-generation aerospace organization developing a fully autonomous aircraft fleet.

The network was implemented using **Cisco Packet Tracer** and includes multiple operational units such as:

* Command Center / HQ
* AI Navigation Unit
* Aircraft Simulation Lab
* Maintenance Hangar
* Emergency Control Node

---

## Project Overview

The Federal Flight Agency Network is designed to support secure, reliable, and low-latency communication between critical aerospace systems. The network includes real-time telemetry, AI navigation support, ground command stations, secure service hosting, and emergency backup communication.

The design follows strict segmentation, controlled routing, redundancy, and failover requirements. Default routes were avoided, and specific static and dynamic routing methods were used to control traffic flow.

---

## Major Features

* Complete Cisco Packet Tracer implementation
* VLSM-based IP addressing
* Logical segmentation for each unit and sub-unit
* Static routing and RIPv2 dynamic routing
* Floating static route for backup path
* DHCP server for Simulation Core
* DHCP relay for Testing Sandbox
* Router-based DHCP for AI and Hangar sub-units
* Static addressing for HQ and Emergency Node
* Centralized DNS and Web services hosted in HQ
* SMTP and POP3 email configuration
* Controlled redundancy between AI Unit and HQ
* No default routes used
* End-to-end connectivity validation

---

## Network Units

| Main Unit               | Sub-Units                        |
| ----------------------- | -------------------------------- |
| Command Center          | HQ Control Wing                  |
| AI Navigation Unit      | ML Engine, Data Processing Cell  |
| Aircraft Simulation Lab | Simulation Core, Testing Sandbox |
| Maintenance Hangar      | Diagnostics Bay, Repair Unit     |
| Emergency Control Node  | Emergency Node                   |

---

## Base Network

The base network used for this project is:

```text
10.1.0.0/16
```

VLSM subnetting was applied based on the required number of hosts for each unit and sub-unit.

---

## VLSM Summary

| Segment                               | Needed Hosts | Prefix | Network Address | Subnet Mask     |
| ------------------------------------- | -----------: | -----: | --------------- | --------------- |
| HQ Control Wing                       |         2000 |    /21 | 10.1.0.0        | 255.255.248.0   |
| Simulation Core                       |          600 |    /22 | 10.1.8.0        | 255.255.252.0   |
| Testing Sandbox                       |          600 |    /22 | 10.1.12.0       | 255.255.252.0   |
| ML Engine                             |          425 |    /23 | 10.1.16.0       | 255.255.254.0   |
| Data Processing Cell                  |          425 |    /23 | 10.1.18.0       | 255.255.254.0   |
| Diagnostics Bay                       |          300 |    /23 | 10.1.20.0       | 255.255.254.0   |
| Repair Unit                           |          300 |    /23 | 10.1.22.0       | 255.255.254.0   |
| Emergency Node                        |           80 |    /25 | 10.1.24.0       | 255.255.255.128 |
| HQ to Simulation Core                 |            2 |    /30 | 10.1.24.128     | 255.255.255.252 |
| HQ to Emergency                       |            2 |    /30 | 10.1.24.132     | 255.255.255.252 |
| Simulation Core to Simulation Sandbox |            2 |    /30 | 10.1.24.136     | 255.255.255.252 |
| Backbone                              |    4 routers |    /29 | 10.1.24.144     | 255.255.255.248 |

---

## Services Configured

### DNS and Web Server

The HQ network hosts the centralized DNS and Web server.

Configured web address:

```text
www.federalfgt.control
```

The web page displays:

```text
Autonomous Flight Control System Active
```

### Email Services

Email communication was configured using **SMTP** and **POP3** between:

```text
mail.hq.federal
mail.ai.federal
```

---

## DHCP Design

| Area                 | DHCP Method                     |
| -------------------- | ------------------------------- |
| Simulation Core      | DHCP Server                     |
| Testing Sandbox      | DHCP Relay                      |
| ML Engine            | Router-based DHCP from R-AI     |
| Data Processing Cell | Router-based DHCP from R-AI     |
| Diagnostics Bay      | Router-based DHCP from R-Hangar |
| Repair Unit          | Router-based DHCP from R-Hangar |
| HQ Control Wing      | Static IP                       |
| Emergency Node       | Static IP only                  |

---

## Routing Design

* HQ to Emergency Node uses next-hop static routing.
* Emergency Node to HQ uses static routing.
* Simulation Lab routers use static routing toward HQ.
* RIPv2 is used between Simulation Lab, AI Unit, and Hangar networks.
* Emergency Node does not participate in dynamic routing.
* A floating static route is configured from AI Unit to HQ through Simulation Sandbox.
* No default routes were used.
* Routing was designed to prevent loops and maintain controlled redundancy.

---

## Repository Contents

| File                               | Description                             |
| ---------------------------------- | --------------------------------------- |
| `Project_Topic3_Group1904_19.pkt`  | Cisco Packet Tracer implementation file |
| `Project_Topic3_Group1904_19.pdf`  | Final project report                    |
| `Screenshot 2026-05-01 202059.png` | Network topology screenshot             |
| `README.md`                        | Project documentation                   |
| `LICENSE`                          | Project license                         |

---

## Tools and Technologies Used

* Cisco Packet Tracer
* VLSM Subnetting
* Static Routing
* RIPv2 Dynamic Routing
* DHCP and DHCP Relay
* DNS
* HTTP/HTTPS
* SMTP/POP3
* Network Troubleshooting

---

## Learning Outcomes

Through this project, we gained practical experience in:

* Designing a large-scale segmented network
* Applying VLSM based on host requirements
* Configuring routers and switches in Cisco Packet Tracer
* Implementing static and dynamic routing
* Setting up DHCP, DNS, Web, and Email services
* Troubleshooting end-to-end network connectivity
* Designing redundant paths without using default routes

---

## Group Members

| Name                | Student ID |
| ------------------- | ---------- |
| Mustavi Hasan       | 22301258   |
| Pranto Roy          | 22301261   |
| Shamaila Sadat Niha | 22301728   |

---

## Course Information

**Course:** CSE421 - Computer Networks
**University:** BRAC University
**Project Topic:** Federal Flight Agency Network
**Group:** 1904
