# Phase 2 Implementation Summary

## CORE-SW
- Catalyst 3560 multilayer switch
- `ip routing` enabled
- SVIs for VLANs 10, 20, 30, 40, 50 and 99
- Inter-VLAN routing performed at the core
- Gi1/0/1 routed to R1 at 172.30.2.190/30
- Default route via 172.30.2.189

## Access switches
### SW-ADMIN
- VLAN 10
- Fa0/1-Fa0/3 for Admin PCs
- Gi0/1 trunk
- Native VLAN 99
- Management IP 172.30.2.162/28

### SW-SALES
- VLAN 20
- Fa0/1-Fa0/4 for POS devices
- Gi0/1 trunk
- Native VLAN 99
- Management IP 172.30.2.163/28

### SW-WAREHOUSE
- VLAN 30
- Fa0/1-Fa0/2 for Warehouse PCs
- Gi0/1 trunk
- Native VLAN 99
- Management IP 172.30.2.164/28

## Wireless
- AP1 and AP2 on VLAN 40
- SSID: `Tlou-Staff-WiFi`
- WPA2-PSK
- AES
- Staff laptop connected and tested

## Server
- SERVER1: 172.30.2.178/29
- Gateway: 172.30.2.177

## R1
- Gi0/0/1 to CORE-SW: 172.30.2.189/30, NAT inside
- Gi0/0/0 to ISP: 172.30.2.185/30, NAT outside
- Static route to internal /23 via 172.30.2.190
- Default route via 172.30.2.186
- NAT/PAT overload enabled
