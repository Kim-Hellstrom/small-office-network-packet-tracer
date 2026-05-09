# SOHO Network Simulation — Cisco Packet Tracer

A simulated Small Office Home Office (SOHO) network built in Cisco Packet Tracer, demonstrating real-world networking concepts including VLAN segmentation, inter-VLAN routing and DHCP configuration.

---

## 🖧 Network Overview

| Device | Role |
|--------|------|
| Cisco 2960-24TT Switch | Layer 2 switching, VLAN segmentation |
| Cisco 2911 Router | Inter-VLAN routing (Router on a Stick) |
| 4 x PC-PT End Devices | Simulated office users |

---

## 👥 VLAN Structure

| VLAN | Name | Users | Subnet |
|------|------|-------|--------|
| VLAN 20 | IT | My PC | 192.168.20.0/24 |
| VLAN 10 | Staff | Tom, Mary, Kenny | 192.168.10.0/24 |

---

## 🔧 What Was Built

### Stage 1 — Basic LAN
Connected two PCs via a Cisco switch using copper straight-through cables. Verified connectivity with successful ICMP ping tests.

![Stage 1](screenshots/stage1/pinging-1-PC.png)

### Stage 2 — VLAN Segmentation
Configured two VLANs on the switch using Cisco IOS CLI commands. Assigned access ports per VLAN and verified isolation between IT and Staff networks.

![VLAN Isolation](screenshots/stage2/seperate-vlans.png)

### Stage 3 — Inter-VLAN Routing (Router on a Stick)
Added a Cisco 2911 router and configured sub-interfaces on GigabitEthernet0/0 using 802.1Q encapsulation. Configured Fa0/5 as a trunk port on the switch to carry all VLANs to the router.

![Inter-VLAN Routing](screenshots/stage3/Confirm-connection.png)

### Stage 4 — DHCP
Configured the router as a DHCP server with separate pools for each VLAN. Verified that all PCs received correct IP addresses automatically.

![DHCP](screenshots/stage4/switch-to-dhcp.png)

---

## 💻 Key Commands Used

```bash
# VLAN Configuration
switchport mode access
switchport access vlan [id]

# Trunk Port
switchport mode trunk

# Sub-interface (Router on a Stick)
encapsulation dot1q [vlan-id]

# DHCP
ip dhcp pool [name]
network [address] [mask]
default-router [gateway]
ip dhcp excluded-address [ip]
```

---

## 📚 Concepts Demonstrated

- LAN design and IP addressing
- VLAN segmentation and access port configuration
- 802.1Q trunking
- Router on a Stick inter-VLAN routing
- DHCP server configuration
- Cisco IOS CLI navigation

---

## 🛠 Tools Used

- Cisco Packet Tracer
- Cisco IOS CLI
- ICMP (ping) for connectivity verification

---

*Built as part of a self-directed learning path toward a junior IT support and network technician role.*
