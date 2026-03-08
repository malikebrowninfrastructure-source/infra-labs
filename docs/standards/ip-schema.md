# IP Addressing Schema

This document defines the addressing plan used in the lab environment.

---

## Network Design Goals

- clear segmentation
- predictable addressing
- scalable subnet structure

---

## Addressing Plan

| VLAN | Network | Gateway | Purpose |
|-----|------|------|------|
| VLAN10 | 10.10.10.0/24 | 10.10.10.1 | Management |
| VLAN20 | 10.10.20.0/24 | 10.10.20.1 | Lab servers |
| VLAN30 | 10.10.30.0/24 | 10.10.30.1 | Clients |

---

## Static Infrastructure Addresses

| Device | IP |
|------|------|
Firewall | 10.10.10.1 |
Switch | 10.10.10.2 |
Proxmox Host | 10.10.10.50 |

---

## DHCP Allocation

Example ranges:
VLAN10: 10.10.10.100 - 10.10.10.200
VLAN20: 10.10.20.100 - 10.10.20.200
VLAN30: 10.10.30.100 - 10.10.30.200
---

## Reserved Infrastructure 10.10.x.1   gateway
10.10.x.2   switch
10.10.x.10  infrastructure
10.10.x.50  hypervisors
This ensures predictable network layout.
