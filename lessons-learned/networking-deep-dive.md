# Networking Deep Dive — Week 01

## Overview

This week focused on building a segmented infrastructure lab using:

- OPNsense firewall
- managed Layer 2 switch
- Proxmox virtualization host
- Linux workstation

The goal was to develop practical networking troubleshooting skills and understand VLAN-based network design.

---

# Major Skills Developed

During this lab work the following skills were practiced:

- VLAN configuration
- switch port tagging and PVID behavior
- firewall gateway routing
- Linux networking diagnostics
- structured troubleshooting methodology

---

# Key Networking Concepts Learned

## VLAN Tagging

Tagged traffic allows multiple VLANs to traverse a single trunk link.

Used for connections between:

- switch and firewall
- switch and Proxmox host

---

## Access Ports

End devices typically connect to access ports.

Access ports:

- belong to a single VLAN
- send and receive untagged traffic

Example:

Management laptop connected to VLAN10.

---

## PVID (Port VLAN ID)

The PVID determines which VLAN untagged traffic is assigned to.

Incorrect PVID settings caused multiple connectivity issues during the lab.

---

## Inter-VLAN Routing

Traffic between VLANs must be routed through the firewall.

Example:
VLAN10 → Firewall → VLAN20

Firewall rules determine whether traffic is allowed.

---

## ARP Resolution

Devices must resolve MAC addresses before sending traffic.

When a host does not know the MAC address of a destination:

1. ARP broadcast is sent
2. destination responds with MAC
3. switch forwards frames accordingly

---

# Troubleshooting Lessons

The most important lesson was learning to troubleshoot **layer by layer**.

Instead of making random configuration changes, a structured approach was used:

1. verify physical connectivity
2. verify interface state
3. verify IP configuration
4. verify routing
5. verify VLAN configuration
6. verify firewall rules
7. verify NAT

This approach dramatically improves troubleshooting efficiency.

---

# Common Problems Encountered

Several issues occurred during lab deployment:

- loss of switch management access
- firewall GUI becoming unreachable
- VM unable to reach gateway
- VM unable to reach internet
- incorrect VLAN membership
- incorrect switch port configuration

Each issue required systematic troubleshooting to resolve.

---

# Key Takeaways

Important principles reinforced during this exercise:

- network segmentation increases complexity
- documentation is critical for troubleshooting
- small configuration errors can cause large failures
- structured troubleshooting prevents random changes

---

# Outcome

By the end of this lab session:

- VLAN segmentation was successfully deployed
- firewall routing was operational
- lab virtual machines had internet connectivity
- infrastructure management access was restored

The lab environment now provides a strong foundation for:

- infrastructure automation
- cloud networking practice
- DevOps infrastructure experiments






