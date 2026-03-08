# Switch VLAN Membership Summary

This document records switch VLAN configuration.

---

## Port Assignments

| Port | Device | VLAN |
|----|------|------|
| 1 | Firewall | trunk |
| 2 | Proxmox Host | trunk |
| 3 | Management Laptop | VLAN10 |

---

## VLAN10

Management network.

Ports:
1 tagged
2 tagged
3 untagged

---

## VLAN20

Lab network.

Ports:
1 tagged
2 tagged

---

## VLAN30

Client network.

Ports:
1 tagged
2 tagged
---

## PVID Settings

| Port | PVID |
|----|----|
|1|1|
|2|1|
|3|10|

---

## Design Notes

- trunk ports carry multiple VLANs
- access ports belong to a single VLAN
- PVID determines untagged traffic VLAN membership





