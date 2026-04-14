# SD-WAN & ADVPN Lab — Dual Hub Topology

## Lab Overview
This lab simulates a Dual Hub SD-WAN and ADVPN deployment using FortiGate 
firewalls managed by FortiManager. The topology consists of 2 Hubs, 2 Spoke 
sites, and a shared internet segment. 

---

## Topology Summary

| Role | Device | Loopback | WAN1 | WAN2 | LAN |
|---|---|---|---|---|---|
| Hub 1 | HUBFG1 | 172.28.255.253/32 | 10.10.30.5/30 | NA | 192.168.90.0/24 |
| Hub 2 | HUBFG2 | 172.28.255.252/32 | 10.10.30.13/30 | NA | 192.168.91.0/24 |
| Branch 1 | SITEFG1 | 172.28.0.1/32 | 10.10.30.22/30 | 10.10.30.26/30 | 192.168.93.0/24 |
| Branch 2 | SITEFG2 | 172.28.0.2/32 | 10.10.30.29/30 | 10.10.30.34/30 | 192.168.94.0/24 |

---

## Management
- **FortiManager** connected via **port3** to connect via local LAN
- Manages all FortiGate devices centrally

---

## Lab Goals
- [ ] Configure SD-WAN rules on Spoke sites
- [ ] Establish ADVPN tunnels between Hubs and Spokes
- [ ] Verify dynamic shortcut tunnels between Spoke-to-Spoke
- [ ] Test failover between WAN1 and WAN2 on Spoke sites
- [ ] Validate BGP routing over overlay tunne
  
  
> _Note:The LAN architecture limits configuration on hub hosts, so spokes must manually configure the IP address for each hub host during failover.
---

