# Network Validation Tests

This document records validation tests performed after deploying the segmented lab network.

The purpose is to verify that:

- VLAN segmentation is working
- firewall routing is functioning
- NAT allows internet access
- management access is operational

---

# Test Environment

| Component | Address |
|---|---|
Firewall (OPNsense) | 10.10.10.1 |
Switch | 10.10.10.2 |
Proxmox Host | 10.10.10.50 |
Management Laptop | 10.10.10.141 |
Lab VM (Ubuntu Server) | 10.10.20.x |

---

# Test 1 — Management VLAN Connectivity

### Objective

Verify management network connectivity between infrastructure devices.

### Test

From management workstation:
ping 10.10.10.1
ping 10.10.10.2
ping 10.10.10.50

### Expected Result

All infrastructure devices respond.

### Result

Success.

---

# Test 2 — VLAN Gateway Reachability

### Objective

Verify hosts can reach their gateway.

### Test

From VM in VLAN20:
ping 10.10.20.1

### Expected Result

Firewall gateway responds.

### Result

Success.

---

# Test 3 — Inter-VLAN Firewall Control

### Objective

Confirm VLAN routing is controlled by firewall policies.

### Test

From VLAN20 host:
ping 10.10.10.1
### Expected Result

Depends on firewall policy configuration.

Traffic should only pass if explicitly permitted.

---

# Test 4 — Internet Connectivity

### Objective

Verify outbound NAT and routing.

### Test

From VLAN20 VM:
ping 8.8.8.8

### Expected Result

Successful replies.

### Result

Success.

---

# Test 5 — DNS Resolution

### Objective

Verify DNS resolution works for internal hosts.

### Test
nslookup google.com
### Expected Result

Domain resolves to IP address.

---

# Test 6 — Management Access

### Objective

Verify administrative interfaces are reachable.

### Test

Access via browser:
https://10.10.10.1
https://10.10.10.2
https://10.10.10.50:8006

### Expected Result

All management interfaces accessible.

---

# Validation Conclusion

The lab infrastructure successfully supports:

- VLAN segmentation
- firewall routing
- outbound internet access
- management network access

This environment is now ready for additional infrastructure experiments and service deployments.




