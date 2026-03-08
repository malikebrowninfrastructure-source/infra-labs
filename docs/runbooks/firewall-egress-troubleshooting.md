# Runbook: Firewall Egress Troubleshooting

This runbook documents how to diagnose situations where hosts cannot reach the internet.

---

## Symptoms

Examples:

- VM can reach gateway but not internet
- ping 8.8.8.8 fails
- DNS resolution fails
- traceroute stops at firewall

---

## Step 1 — Verify IP Configuration

Linux:
ip a
ip route

Verify:

- correct IP address
- correct subnet
- correct default gateway

---

## Step 2 — Test Gateway Connectivity
ping 10.10.20.1

If this fails, issue exists within the VLAN network.

---

## Step 3 — Test External Connectivity
ping 8.8.8.8
If gateway works but internet fails, investigate firewall.

---

## Step 4 — Check Firewall Rules

Verify rules allow outbound traffic.

Example:
Source: VLAN20 net
Destination: any
Action: pass
---

## Step 5 — Verify NAT

Outbound NAT must translate internal networks.

Check:

Firewall → NAT → Outbound

Ensure network appears in NAT rules:
10.10.20.0/24
---

## Step 6 — Test DNS
nslookup google.com or dig google.com
---

## Common Causes

| Problem | Cause |
|------|------|
No internet | Missing NAT rule |
DNS fails | DNS server misconfigured |
Gateway unreachable | VLAN misconfiguration |
Packet drops | Firewall rule blocking traffic |
