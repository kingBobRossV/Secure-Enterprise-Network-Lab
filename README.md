# Secure Enterprise Network Lab

## Objective

The Secure Enterprise Network Lab project aimed to design and implement a segmented small-enterprise network with foundational security controls. The primary focus was to apply VLAN segmentation, inter-VLAN routing, and access control policies to reduce lateral movement and enforce least privilege across departments. This hands-on experience was designed to strengthen practical network security engineering skills and demonstrate secure architectural decision-making.

### Skills Learned

Practical implementation of VLAN-based network segmentation.

Configuration of inter-VLAN routing using Router on a Stick (ROAS).

Development and application of standard and extended Access Control Lists (ACLs).

Switch hardening techniques including port security and disabling unused ports.

Secure management plane configuration using SSH and encrypted credentials.

Application of the Principle of Least Privilege in network design.

Documentation and validation of security controls.

### Tools Used

Cisco Packet Tracer for network simulation and design.

Cisco IOS CLI for device configuration and management.

VLAN configuration and 802.1Q trunking.

Standard and Extended Access Control Lists (ACLs).

SSH for secure remote device administration.

## Steps

*Ref 1: Network Diagram*

Designed a segmented enterprise topology including User, Server, and Management VLANs connected via a trunk link to a router configured for inter-VLAN routing.

*Ref 2: VLAN Configuration*

Created VLANs for Users (VLAN 10), Servers (VLAN 20), and Management (VLAN 30). Assigned switch access ports appropriately and configured trunking between the switch and router.

*Ref 3: Inter-VLAN Routing (Router on a Stick)*

Configured router subinterfaces using 802.1Q encapsulation and assigned default gateway IP addresses for each VLAN.

*Ref 4: Access Control Implementation*

Applied extended ACLs to restrict traffic between VLANs. Allowed only necessary services from Users to Servers while denying access to the Management VLAN. Verified policy enforcement through connectivity testing.

*Ref 5: Switch and Device Hardening*

Disabled unused switch ports, implemented port security limiting MAC addresses per port, enabled SSH-only remote access, encrypted device passwords, and configured login banner warnings.

*Ref 6: Security Validation*

Performed connectivity testing to confirm segmentation effectiveness and validated that unauthorized inter-VLAN communication was successfully blocked.
