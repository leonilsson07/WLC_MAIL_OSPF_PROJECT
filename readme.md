# WLC_MAIL_OSPF_PROJECT

## Project Overview

This Cisco Packet Tracer project simulates a **multi-site enterprise wireless network** using **OSPF routing**, **Wireless LAN Controllers (WLC)**, and **centralized mail and DNS services**. The network connects two locations—**Västerås** and **Stockholm**—over a routed point-to-point WAN link and demonstrates realistic enterprise design principles used in campus and branch environments.

The project focuses on **dynamic routing**, **role-based wireless access (Teacher / Student)**, and **centralized infrastructure services**, closely reflecting real-world enterprise deployments.

* **Date Completed:** February 2025
* **Tools Used:** Cisco Packet Tracer

---

## Network Topology

The topology consists of two geographically separated sites:

* **Västerås (Main Site)**
* **Stockholm (Branch Site)**

Each site includes:

* A router participating in OSPF
* Access switches
* A Wireless LAN Controller (WLC)
* Multiple lightweight access points
* Wired and wireless end devices

The sites are interconnected using a /30 point-to-point WAN link.

---

## Inter-Site WAN Link

| Link      | IP Address | Subnet Mask     | Description        |
| --------- | ---------- | --------------- | ------------------ |
| Västerås  | 10.0.0.1   | 255.255.255.252 | Point-to-point WAN |
| Stockholm | 10.0.0.2   | 255.255.255.252 | Point-to-point WAN |

This design minimizes address waste and mirrors real WAN routing practices.

---

## VLANs and IP Addressing

### Västerås

| Network | Gateway      | DNS          | DHCP Start    | Subnet Mask   |
| ------- | ------------ | ------------ | ------------- | ------------- |
| Student | 192.168.10.1 | 192.168.99.5 | 192.168.10.30 | 255.255.255.0 |
| Teacher | 192.168.20.1 | 192.168.99.5 | 192.168.20.30 | 255.255.255.0 |

### Stockholm

| Network | Gateway      | DNS          | DHCP Start    | Subnet Mask   |
| ------- | ------------ | ------------ | ------------- | ------------- |
| Student | 192.168.60.1 | 192.168.99.5 | 192.168.60.30 | 255.255.255.0 |
| Teacher | 192.168.70.1 | 192.168.99.5 | 192.168.70.30 | 255.255.255.0 |

---

## Routing Protocol

### OSPF

* **Protocol:** OSPFv2
* **Area:** 0 (Backbone)
* **Purpose:**

  * Dynamic route exchange between Västerås and Stockholm
  * Automatic failover and scalability
  * Realistic enterprise routing behavior

All internal VLAN networks and the WAN /30 link are advertised into OSPF.

---

## Wireless Architecture

### Wireless LAN Controller (WLC)

* Centralized wireless management
* SSID-to-VLAN mapping for Teachers and Students
* Lightweight AP registration and control

### Access Points

* Separate APs for Teacher and Student coverage
* Clients receive IP configuration via DHCP
* Traffic is segmented based on user role

---

## Mail, DNS, and DHCP Services

### Email

* Each device is assigned an email address
* Role-based accounts:

  * Students
  * Teachers
  * Admin

### DNS

* Internal domain: `grilska.se`
* Name resolution for:

  * Mail servers
  * Network devices
  * Client systems

### DHCP

* Centralized DHCP server
* Automatic IP assignment per VLAN

---

## Project Features

* Multi-site enterprise topology
* OSPF dynamic routing
* Wireless LAN Controller deployment
* VLAN-based role separation
* Centralized DHCP, DNS, and Mail services
* End-to-end connectivity across sites

---

## Skills Demonstrated

* Cisco Packet Tracer network simulation
* Enterprise wireless design (WLC + APs)
* OSPF configuration and troubleshooting
* VLAN and subnet planning
* WAN point-to-point addressing
* Network service integration (DNS, DHCP, Mail)

---

## Files Included

* **WLC_MAIL_OSPF_PROJECT.pkt** – Cisco Packet Tracer project file
* **README.md** – Project documentation

---

## How to Use

1. Open `WLC_MAIL_OSPF_PROJECT.pkt` in Cisco Packet Tracer
2. Verify OSPF neighbor relationships
3. Check routing tables on both routers
4. Connect wireless clients and confirm correct VLAN assignment
5. Test inter-site connectivity
6. Verify email and DNS functionality

---

## Potential Improvements

* Inter-VLAN ACLs for role-based security
* WPA2/WPA3 authentication with RADIUS
* Redundant WAN links with OSPF cost tuning
* Network monitoring using SNMP and Syslog

---

## Author

Leo Nilsson
Enterprise networking lab project showcasing wireless, routing, and infrastructure services.
