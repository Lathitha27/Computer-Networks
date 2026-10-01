# Project Reflection

The Phase 2 build converted the Phase 1 network design into a working Cisco Packet Tracer implementation.

The main lesson was the importance of validating physical connectivity against logical configuration. Native VLAN mismatches caused Spanning Tree consistency errors, and R1 initially had the correct IP addresses on the wrong physical interfaces. Verification commands such as `show interfaces trunk`, `show ip interface brief`, and `show cdp neighbors` were essential for finding and fixing those issues.

The wireless security requirement was successfully implemented using WPA2-PSK with AES. The final network demonstrated VLAN segmentation, DHCP, inter-VLAN routing, server connectivity, wireless access, NAT/PAT, ISP simulation, and end-to-end connectivity.
