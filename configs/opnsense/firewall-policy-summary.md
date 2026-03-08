# Firewall Policy Summary

This document summarizes firewall rules configured in OPNsense.

---

## VLAN10 (Management)

Rules: allow management network → any
Used for:

- SSH
- administration
- infrastructure access

---

## VLAN20 (Lab Servers)

Rules:
allow VLAN20 → internet
block VLAN20 → management

Purpose:

Lab workloads should not access infrastructure.

---

## VLAN30 (Clients)

Rules:
allow client → internet
restricted access to other VLANs

---

## NAT

Outbound NAT enabled for:
10.10.10.0/24
10.10.20.0/24
10.10.30.0/24

Allows private networks to access the internet.








