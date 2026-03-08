2"}
# Current Lab Topology

## Overview

The infrastructure lab environment consists of a Proxmox virtualization host connected to a managed switch and protected by an OPNsense firewall. Network segmentation is implemented using VLANs.

The environment is designed to simulate enterprise infrastructure patterns including network isolation, firewall enforcement, and controlled access between network segments.

---

## Physical Topology

Ubuntu Control Workstation  
↓  
Managed Switch  
↓  
OPNsense Firewall  
↓  
ISP Router  

Proxmox host is connected to the managed switch and hosts virtual machines used for lab exercises.

---

## Core Components

### Firewall
OPNsense firewall provides:

- gateway routing
- firewall policy enforcement
- outbound NAT
- inter-VLAN traffic control

### Switch

Managed Layer 2 switch provides:

- VLAN segmentation
- trunking for virtualization host
- port-based VLAN access

### Proxmox Host

The Proxmox host provides virtualization and runs multiple lab VMs used for networking and Linux exercises.

---

## VLAN Structure

| VLAN | Purpose |
|-----|--------|
| VLAN 10 | Management network |
| VLAN 20 | Lab / server network |
| VLAN 30 | Client / testing network |

---

## Key Infrastructure Goals

The topology supports testing of:

- firewall policy enforcement
- inter-VLAN routing
- NAT behavior
- Linux network troubleshooting
- infrastructure failure analysis
  
