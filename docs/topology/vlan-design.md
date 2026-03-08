003"}
# VLAN Design

## Overview

Network segmentation is implemented using VLANs to simulate enterprise-style network separation between infrastructure components, services, and client devices.

Each VLAN represents a separate security boundary and traffic between VLANs is controlled by firewall policy.

---

## VLAN 10 – Management Network

Purpose:

Provides administrative access to infrastructure components.

Typical devices:

- Proxmox host
- network switch management interface
- firewall management interface
- control workstation

Security goal:

Limit access to trusted administrative devices only.

---

## VLAN 20 – Lab / Server Network

Purpose:

Hosts virtual machines used for infrastructure experiments and server deployments.

Typical devices:

- Ubuntu server VMs
- application test servers
- infrastructure testing workloads

Security goal:

Allow outbound internet access but restrict direct access to management network.

---

## VLAN 30 – Client Network

Purpose:

Simulates user endpoints or external clients interacting with services.

Typical devices:

- client test VMs
- attack simulation machines
- endpoint testing systems

Security goal:

Limit access to internal infrastructure while allowing testing of service access patterns.

---

## Firewall Policy Model

Traffic between VLANs is controlled using firewall rules.

Examples:

VLAN 10 → VLAN 20  
Allowed for administrative access (SSH, RDP)

VLAN 20 → VLAN 10  
Blocked to protect management systems

VLAN 30 → VLAN 20  
Allowed only for service testing

VLAN 30 → VLAN 10  
Blocked 
