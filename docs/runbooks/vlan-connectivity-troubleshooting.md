# Runbook: VLAN Connectivity Troubleshooting

## Problem

Virtual machines deployed in VLAN networks may fail to reach the gateway or internet.

---

## Symptoms

Examples observed during lab:

- VM cannot ping gateway
- VM cannot reach internet
- firewall GUI unreachable
- switch management interface unreachable

---

## Layered Troubleshooting Process

### Step 1 — Physical Layer

Verify cables and link lights.

Check switch port status.

---

### Step 2 — Interface Configuration

On Linux host or VM:

ip a

Verify correct IP address and interface state.

---

### Step 3 — Routing

Check default route.

ip route

Confirm gateway address is correct.

---

### Step 4 — Gateway Connectivity

Test reachability of gateway.

ping 10.10.x.1

---

### Step 5 — VLAN Configuration

Verify switch port VLAN membership.

Common issues:

- port missing VLAN membership
- incorrect PVID
- multiple untagged VLAN assignments

---

### Step 6 — Firewall Policy

Verify firewall rules allow traffic between VLANs or to WAN.

---

### Step 7 — NAT Configuration

If internet access fails but gateway is reachable, verify outbound NAT configuration.

---

## Common Root Causes

Most connectivity failures in this lab environment were caused by:

- incorrect VLAN tagging
- switch port not configured as VLAN member
- incorrect PVID assignment
