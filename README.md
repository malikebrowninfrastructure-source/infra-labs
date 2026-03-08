# Infrastructure Labs

## Overview

This repository documents hands-on infrastructure labs focused on networking, firewall policy, virtualization, and Linux systems administration.

The lab environment is designed to simulate real-world infrastructure engineering tasks including network segmentation, routing, firewall policy design, troubleshooting, and operational documentation.

Rather than focusing on theoretical concepts, these labs emphasize building, breaking, diagnosing, and repairing infrastructure components while documenting the process through engineering artifacts.

---

## Lab Goals

The purpose of this lab environment is to build strong foundational skills in:

- Linux systems administration
- Network segmentation using VLANs
- Firewall rule design and traffic control
- NAT behavior and outbound connectivity
- Infrastructure troubleshooting methodology
- Operational documentation practices
- Change control and validation procedures

These labs are intended to develop practical infrastructure intuition similar to real-world enterprise environments.

---

## Lab Environment

### Hardware

- Proxmox Virtualization Host
- OPNsense Firewall
- Managed Layer 2 Switch (VLAN capable)
- Ubuntu Linux Control Workstation
- Raspberry Pi 4
- MeLe Mini PC

### Core Components

- Proxmox VE
- OPNsense Firewall
- VLAN segmentation
- Ubuntu Server virtual machines

---

## Network Architecture

The lab network is segmented using VLANs to simulate enterprise network boundaries.

| VLAN | Purpose |
|-----|--------|
| VLAN 10 | Management network |
| VLAN 20 | Lab / server network |
| VLAN 30 | Client / testing network |

Segmentation allows testing of routing, firewall policy enforcement, and access control between network zones.

---

## Repository Structure

infra-labs/
├── docs/  
│   ├── topology/  
│   ├── runbooks/  
│   ├── change-records/  
│   └── standards/  

├── diagrams/  

├── configs/  
│   ├── proxmox/  
│   ├── opnsense/  
│   └── switch/  

├── validation/  

└── lessons-learned/

---

## Documentation Approach

All infrastructure work is documented using several artifact types:

### Topology Documentation
Explains the physical and logical layout of the network.

### Change Records
Tracks configuration changes and deployment steps.

### Runbooks
Documents troubleshooting procedures and root cause analysis.

### Validation Tests
Confirms infrastructure functionality and network segmentation.

### Lessons Learned
Captures insights gained from troubleshooting and lab experimentation.

---

## Status

This lab environment is under continuous development as part of ongoing infrastructure engineering practice
