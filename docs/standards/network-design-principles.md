# Network Design Principles

These principles guide the design of the lab infrastructure.

---

## 1 — Segmentation

Networks are separated into VLANs to:

- reduce broadcast domains
- isolate services
- improve security

---

## 2 — Default Deny Security

Firewall policies should follow:
deny by default
allow only required traffic
---

## 3 — Management Isolation

Management interfaces should exist in a dedicated VLAN.

Benefits:

- reduces attack surface
- limits administrative access

---

## 4 — Least Privilege Connectivity

VLANs should only communicate when required.

Example:
VLAN10 → VLAN20 (SSH)
VLAN20 → VLAN10 (blocked)
---

## 5 — Deterministic Addressing

Use predictable addressing for infrastructure devices.

Example:
gateway = .1
switch = .2
hypervisor = .50
---

## 6 — Observable Infrastructure

All infrastructure should allow easy troubleshooting through:

- logs
- structured addressing
- documented topology


