# Secure Enterprise Network Lab

## Objective

The Secure Enterprise Network Lab project aimed to design and implement a segmented small-enterprise network with foundational security controls. The primary focus was to apply VLAN segmentation, inter-VLAN routing, and access control policies to reduce lateral movement and enforce least privilege across departments. This hands-on experience was designed to strengthen practical network security engineering skills and demonstrate secure architectural decision-making.

Security controls were tested using simulated unauthorized access attempts. VLAN segmentation prevented lateral movement, ACL policies restricted inter-VLAN communication, port security limited unauthorized devices, and SSH-only management ensured encrypted administrative access.

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

<p><img width="929" height="615" alt="0 Architecture Overview" src="https://github.com/user-attachments/assets/4e59ba38-97b0-47bd-9e05-3049c5687356" /></p>

*Ref 2: VLAN Configuration*

Created VLANs for Users (VLAN 10), Servers (VLAN 20), and Management (VLAN 30). Assigned switch access ports appropriately and configured trunking between the switch and router.

<p><img width="444" height="389" alt="1 Switch Interface Configuration" src="https://github.com/user-attachments/assets/0c5c1765-661c-4791-9f81-33d7cad17a9a" /></p>

<p><img width="583" height="273" alt="2 VLAN Brief" src="https://github.com/user-attachments/assets/566d9c9e-600b-4b58-9777-0dd1a929e2b1" /></p>

<p><img width="534" height="209" alt="3 Interfaces Trunk" src="https://github.com/user-attachments/assets/aa92f76b-79cf-4115-80e9-fd3c363dace9" /></p>   

*Ref 3: Inter-VLAN Routing (Router on a Stick)*

Configured router subinterfaces using 802.1Q encapsulation and assigned default gateway IP addresses for each VLAN.

<p><img width="633" height="816" alt="4 Router Trunk" src="https://github.com/user-attachments/assets/87d297f1-e75c-4b35-8398-977693e6d39d" /></p>

*Ref 4: Access Control Implementation*

Applied extended ACLs to restrict traffic between VLANs. Allowed only necessary services from Users to Servers while denying access to the Management VLAN. Verified policy enforcement through connectivity testing.

<p><img width="637" height="180" alt="5 ACL Config" src="https://github.com/user-attachments/assets/ac18fcb3-863b-4806-8fcf-f9e27f971971" /></p>

<p><img width="517" height="113" alt="6 ACL Confirm" src="https://github.com/user-attachments/assets/cfef7907-d311-4ab6-af80-e97c448d4bc9" /></p>    


Confirming that ACL is working as intended.  Used telnet for confirmation that HTTP/HTTPS specifically was working and nothing else since packet tracer doesn't allow pings to specific ports

<p><img width="448" height="431" alt="7 ACL Working" src="https://github.com/user-attachments/assets/929cdac4-5fc7-46ab-91de-eb3791355686" /></p>

*Ref 5: Switch and Device Hardening*

Disabled unused switch ports, implemented port security limiting MAC addresses per port, enabled SSH-only remote access, encrypted device passwords, and configured login banner warnings.

<p><img width="469" height="385" alt="8 Port security" src="https://github.com/user-attachments/assets/abe565db-fb96-44cb-b0f2-e3a305047884" /></p>    

<p><img width="533" height="255" alt="9 Forcing SSH" src="https://github.com/user-attachments/assets/a7468cdf-5fad-42e5-b10c-963accb4389a" /></p>

<p><img width="333" height="255" alt="10 Port security confirmation" src="https://github.com/user-attachments/assets/2ac62f0a-2ebf-485b-88d6-b89f7c83776e" /></p>

<p><img width="448" height="431" alt="7 ACL Working" src="https://github.com/user-attachments/assets/3d68cfbb-7b41-4057-a442-dd94e4818c37" /></p>

*Ref 6: Security Validation*

Performed connectivity testing to confirm segmentation effectiveness and validated that unauthorized inter-VLAN communication was successfully blocked.

Ping fails due to only http and https being allowed to webserver, Web search succeeds.

<p><img width="446" height="352" alt="12 Ping failure" src="https://github.com/user-attachments/assets/6606fb00-5186-4f71-b295-c6c28335c2ec" /></p>

<p><img width="768" height="324" alt="13 HTTP working" src="https://github.com/user-attachments/assets/67ac2d13-f26e-455f-880c-050fe5a79b17" /></p>

Connecting a new pc to a port to test port security is working

<p><img width="928" height="631" alt="14 New connection to port" src="https://github.com/user-attachments/assets/7274d965-b424-4608-ad72-33e5412415cf" /></p>

<p><img width="714" height="287" alt="15 Port security" src="https://github.com/user-attachments/assets/786b2e6a-a51b-4b1f-9382-1a1780c18b42" /></p>

<p><img width="446" height="255" alt="16 Confirm port security blocked port" src="https://github.com/user-attachments/assets/222b7381-a08f-4685-818b-1eb1e188e64b" /></p>

Ping/SSH from User PC fails but succeeds from Management PC confirming Management Plane is configured properly

<p><img width="517" height="580" alt="17 Users PC SSH Failure" src="https://github.com/user-attachments/assets/bde2fab7-3e96-4a53-bc7d-d710d1b8b85a" /></p>

<p><img width="687" height="724" alt="18 Management PC SSH Success" src="https://github.com/user-attachments/assets/223abf90-57b0-4470-b22f-9ce837ef191f" /></p>


