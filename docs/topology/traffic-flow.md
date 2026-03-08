# Traffic Flow Architecture

This document describes how network traffic flows through the lab infrastructure.

## Infrastructure Components

- OPNsense firewall (default gateway)
- Managed Layer 2 switch
- Proxmox virtualization host
- Management workstation
- Lab virtual machines

---

## Network Segments

| VLAN | Network | Purpose |
|-----|------|------|
| VLAN10 | 10.10.10.0/24 | Management |
| VLAN20 | 10.10.20.0/24 | Lab / servers |
| VLAN30 | 10.10.30.0/24 | Client testing |

---

## Traffic Flow Model

### Same VLAN Traffic

When two devices exist within the same VLAN:

1. Device sends packet to destination IP
2. Device checks ARP table
3. If MAC unknown → ARP request broadcast
4. Switch forwards broadcast within VLAN
5. Destination responds with MAC address
6. Switch forwards frames at Layer 2

Routing is NOT involved.

Example:
Laptop (10.10.10.141)
↓
Switch (L2)
↓
Proxmox Host (10.10.10.50)
---

### Inter-VLAN Traffic

Traffic between VLANs must pass through the firewall.

Example: VLAN10 → VLAN20
Laptop (10.10.10.141)
↓
Switch
↓
Firewall Gateway (10.10.10.1)
↓
Firewall routing decision
↓
Switch
↓
VLAN20 VM (10.10.20.10)

Firewall rules determine whether traffic is permitted.

---

### Internet Traffic

Example: VLAN20 VM → Internet
VM (10.10.20.x)
↓
Switch
↓
Firewall (10.10.20.1)
↓
Firewall NAT
↓
ISP Router
↓
Internet
Outbound NAT translates private addresses before exiting the network.

---

## Security Boundaries

Security enforcement occurs at:

- firewall rules
- VLAN segmentation
- outbound NAT

This ensures lab networks cannot directly access management networks unless explicitly permitted.
