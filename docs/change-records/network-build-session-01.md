# Change Record: Network Build Session 01

## Date
2026-03-08

## Objective

Build a segmented lab network using:

- OPNsense firewall
- managed switch
- Proxmox virtualization host
- VLAN segmentation

The goal was to create a realistic infrastructure environment for practicing networking and infrastructure troubleshooting.

---

## Infrastructure Components

Firewall: OPNsense  
Switch: Managed Layer 2 switch  
Virtualization Host: Proxmox  
Client workstation: Ubuntu Linux laptop

---

## Network Architecture

Gateway: 10.10.0.1

Initial VLAN structure:

| VLAN | Network | Purpose |
|-----|------|------|
| VLAN10 | 10.10.10.0/24 | Management |
| VLAN20 | 10.10.20.0/24 | Lab servers |
| VLAN30 | 10.10.30.0/24 | Client testing |

---

## Work Performed

During this session the following tasks were completed:

- connected firewall, switch, and Proxmox host
- configured switch ports for VLAN membership
- configured Proxmox network bridge
- deployed Ubuntu VM
- configured VM network interface
- verified gateway connectivity
- verified internet connectivity
- practiced layered troubleshooting techniques

---

## Issues Encountered

Multiple connectivity failures occurred during configuration including:

- loss of switch GUI access
- loss of firewall GUI access
- VM unable to reach gateway
- VM unable to reach internet

Each issue was diagnosed and resolved through troubleshooting.

---

## Result

Network infrastructure successfully restored and validated.

VM was able to reach:

- gateway
- internet
- DNS services
