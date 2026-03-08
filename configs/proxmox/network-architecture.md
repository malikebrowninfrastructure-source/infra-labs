# Proxmox Network Architecture

This document describes the network configuration of the Proxmox host.

---

## Physical 
eth0
Connected to switch port.

---

## Linux Bridge
vmbr0
Bridge connects:

- physical NIC
- virtual machine interfaces

---

## Bridge Configuration
auto vmbr0
iface vmbr0 inet static
address 10.10.10.50/24
gateway 10.10.10.1
bridge_ports eth0
bridge_stp off
bridge_fd 0
---

## VLAN Handling

VLAN segmentation is handled by the switch and firewall.

VM interfaces are assigned to specific VLAN bridges when required.

---

## Traffic Path
VM → Proxmox Bridge → Switch → Firewall

Proxmox acts as a Layer 2 bridge for VM network traffic.
