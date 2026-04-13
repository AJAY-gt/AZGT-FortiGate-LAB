# SD-WAN & ADVPN Lab — Dual Hub Topology

## Lab Overview
This lab simulates a Dual Hub SD-WAN and ADVPN deployment using FortiGate 
firewalls managed by FortiManager. The topology consists of 2 Hubs, 2 Spoke 
sites, and a shared internet segment.

---

## Topology Summary

| Role | Device | Loopback | WAN Interface |
|---|---|---|---|
| Hub 1 | HUBR1 | L0: 10.1.1.1 | e0/2 — 10.10.30.4/30 WAN1 |
| Hub 2 | HUBR2 | L0: 10.1.1.2 | e0/2 — 10.10.30.12/30 WAN1 |
| Spoke 1 | SITER1 | L0: 10.1.1.3 | e0/2 — 10.10.30.20/30 WAN1 |
| Spoke 2 | SITER2 | L0: 10.1.1.4 | e0/2 — 10.10.30.28/30 WAN1 |

---

## WAN Underlay — IP Addressing

| Link | Subnet |
|---|---|
| HUBR1 ↔ Net | 10.10.20.4/30 |
| HUBR2 ↔ Net | 10.10.20.8/30 |
| SITER1 ↔ Net | 10.10.20.16/30 |
| SITER2 ↔ Net | 10.10.20.12/30 |

---

## Spoke WAN Interfaces

| Device | WAN1 | WAN2 |
|---|---|---|
| SITEFG1 | 10.10.30.20/30 | 10.10.30.24/30 |
| SITEFG2 | 10.10.30.28/30 | 10.10.30.32/30 |

---

## LAN Segments

| Device | LAN Host | LAN Network |
|---|---|---|
| HUBFG1 | Hub1Host | 172.28.255.253 |
| HUBFG2 | Hub2Host | 172.28.255.252 |
| SITEFG1 | Site1Host | 172.28.0.1 |
| SITEFG2 | Site2Host | 172.28.0.2 |

---

## Management
- **FortiManager** connected via **port1** to the internet segment
- Manages all FortiGate devices centrally

---

## Lab Goals
- [ ] Configure SD-WAN rules on Spoke sites
- [ ] Establish ADVPN tunnels between Hubs and Spokes
- [ ] Verify dynamic shortcut tunnels between Spoke-to-Spoke
- [ ] Test failover between WAN1 and WAN2 on Spoke sites
- [ ] Validate BGP routing over overlay tunnels

---

## Diagram
![Topology](Diagrams/Underlay-Diagram/topology.png)
