# IP Addressing Plan

| VLAN / Link | Purpose | Network | Mask | Gateway / Interfaces |
|---|---|---|---|---|
| VLAN 20 | Sales / POS | 172.30.2.0/26 | 255.255.255.192 | 172.30.2.1 |
| VLAN 10 | Admin / Management | 172.30.2.64/27 | 255.255.255.224 | 172.30.2.65 |
| VLAN 30 | Warehouse / Inventory | 172.30.2.96/27 | 255.255.255.224 | 172.30.2.97 |
| VLAN 40 | Staff Wireless | 172.30.2.128/27 | 255.255.255.224 | 172.30.2.129 |
| VLAN 99 | Network Management | 172.30.2.160/28 | 255.255.255.240 | 172.30.2.161 |
| VLAN 50 | Servers | 172.30.2.176/29 | 255.255.255.248 | 172.30.2.177 |
| R1-ISP | WAN | 172.30.2.184/30 | 255.255.255.252 | R1 .185 / ISP .186 |
| CORE-SW-R1 | Routed link | 172.30.2.188/30 | 255.255.255.252 | R1 .189 / CORE-SW .190 |

Management addresses:
- CORE-SW: 172.30.2.161
- SW-ADMIN: 172.30.2.162
- SW-SALES: 172.30.2.163
- SW-WAREHOUSE: 172.30.2.164

SERVER1:
- 172.30.2.178/29
- Gateway 172.30.2.177
- DNS 8.8.8.8

The 172.30.3.0/24 block remains reserved for the future branch office under CR6.
