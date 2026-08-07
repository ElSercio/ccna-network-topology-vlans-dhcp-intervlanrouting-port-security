# ccna-network-topology-vlans-dhcp-intervlanrouting-port-security
Enterprise network simulation using DHCP, inter vlan routing and port security (pending NAT and ACL)
# Enterprise Network Topology — VLANs, Inter-VLAN Routing, DHCP & Port-Security

This project simulates an enterprise network using VLAN segmentation, 
router-on-a-stick inter-VLAN routing, centralized DHCP, and port-security. 
NAT and ACLs are planned as next steps.

## Topology Overview

- **2x Layer 2 Switches** — connect end devices within each VLAN
- **1x Layer 3 Switch** — works as a transparent vtp device.
- **1x Router** — performs inter-VLAN routing using the router-on-a-stick method
- **3x VLANs**:
  - VLAN 10 — Engineers
  - VLAN 20 — Sales
  - VLAN 30 — Servers

## Key Features

- **Inter-VLAN Routing**: configured via router subinterfaces with 802.1Q 
  encapsulation, allowing communication between VLANs through a single 
  physical link (router-on-a-stick)
- **Centralized DHCP**: a dedicated server in VLAN 30 assigns IP addresses 
  to hosts in VLANs 10 and 20 using `ip helper-address` for DHCP relay
- **Port-Security**: enabled on all access switch ports, restricting each 
  port to a single learned MAC address; violations result in the interface 
  being shut down (violation mode: shutdown)
- Add a simulated ISP router with NAT overload for internet access

## Next Steps

- [ ] Implement ACLs to control traffic between networks.
- [ ] Implement OSPF by adding two different smaller networks.
