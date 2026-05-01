# Enterprise Network Lab: VLAN Segmentation & Inter-VLAN Routing

## Overview

This project simulates a small enterprise network focusing on segmentation, routing, and basic security controls.

The goal is to demonstrate practical networking skills aligned with real-world scenarios, including VLAN configuration, inter-VLAN routing, DHCP services, and access control.

---

## Objectives

* Segment the network using VLANs
* Enable communication between VLANs using Router-on-a-Stick
* Automatically assign IP addresses using DHCP
* Implement basic security using ACLs
* Secure remote access using SSH

---

## Network Topology

<img width="729" height="417" alt="Enterprise-network-lab-vlan-routing-acl" src="https://github.com/user-attachments/assets/95191061-b007-4d3a-bab4-02adc785a082" />


---

##  Technologies Used

* VLANs (802.1Q)
* Inter-VLAN Routing
* DHCP
* Access Control Lists (ACL)
* SSH

---

##  Network Design

| VLAN | Name  | Subnet          |
| ---- | ----- | --------------- |
| 10   | RH    | 192.168.10.0/24 |
| 20   | IT    | 192.168.20.0/24 |
| 30   | GUEST | 192.168.30.0/24 |

---

##  Security Implementation

An ACL was configured to restrict access from the GUEST VLAN to the IT VLAN, ensuring basic network isolation.

---

## Configuration Files

* Router config: `configs/R1.txt`
* Switch config: `configs/S1.txt`


---

##  Author

Adão Francisco


This lab was built using Cisco Packet Tracer as part of hands-on practice for networking certifications such as CCNA and ENCOR.
