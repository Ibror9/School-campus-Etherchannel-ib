# School-campus-Etherchannel-ib
Cisco Packet Tracer project implementing a redundant school campus network using EtherChannel (LACP, PAgP, and Static), VLAN trunking, and PVST+.
# School Campus EtherChannel Configuration

![Cisco](https://img.shields.io/badge/Cisco-Packet%20Tracer-blue)
![CCNA](https://img.shields.io/badge/CCNA-Switching-success)
![EtherChannel](https://img.shields.io/badge/EtherChannel-LACP%20|%20PAgP%20|%20Static-orange)

## Overview

This project demonstrates the implementation of **EtherChannel** in a redundant **school campus network** using Cisco Packet Tracer.

The network consists of two Core Distribution switches (CD1 and CD2) and two Access switches (ACC3 and ACC4). Three EtherChannel technologies are implemented:

- **LACP (IEEE 802.3ad)**
- **PAgP (Cisco Proprietary)**
- **Static EtherChannel**

PVST+ is configured with **CD1 as the Root Bridge** and **CD2 as the Secondary Root Bridge**.

---

# Network Topology

![School Campus Topology](Images/topology.png)

---

## Device Roles

| Device | Role |
|---------|------|
| CD1 | Core Distribution Switch (Root Bridge) |
| CD2 | Core Distribution Switch (Secondary Root) |
| ACC3 | Access Layer Switch |
| ACC4 | Access Layer Switch |
| PC1 | VLAN 10 Host |
| PC2 | VLAN 10 Host |
| PC3 | VLAN 10 Host |
| PC4 | VLAN 10 Host |

---

## IP Addressing

| Device | IP Address | VLAN |
|---------|------------|------|
| PC1 | 10.10.10.10 | 10 |
| PC2 | 10.10.10.11 | 10 |
| PC3 | 10.10.10.12 | 10 |
| PC4 | 10.10.10.13 | 10 |

---

## EtherChannel Links

| Connection | Interfaces | Protocol |
|------------|------------|----------|
| CD1 ↔ ACC3 | Fa0/23-24 | LACP |
| CD2 ↔ ACC3 | Fa0/21-22 | LACP |
| CD1 ↔ ACC4 | Fa0/21-22 | PAgP |
| CD2 ↔ ACC4 | Fa0/23-24 | PAgP |
| CD1 ↔ CD2 | Gi0/1-2 | Static EtherChannel |

---

## Spanning Tree

| Switch | Priority | Role |
|---------|---------:|------|
| CD1 | 24576 | Root Bridge |
| CD2 | 28672 | Secondary Root |

---

## Native VLAN

199

---

## Access VLAN

10

---

## Verification

```bash
show etherchannel summary
show interfaces trunk
show spanning-tree
show spanning-tree root
show interfaces status
```

---

## Technologies

- Cisco Packet Tracer
- EtherChannel
- LACP
- PAgP
- Static EtherChannel
- PVST+
- VLANs
- 802.1Q Trunking
- Layer 2 Switching

---

## Learning Outcomes

- Configure LACP EtherChannel
- Configure PAgP EtherChannel
- Configure Static EtherChannel
- Configure VLAN trunks
- Configure Native VLAN
- Configure PVST+
- Verify redundancy and load balancing
