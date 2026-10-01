# CMPG325 Network Design Project - Tlou Furniture & Appliances

Individual network design and Cisco Packet Tracer implementation for CMPG 325, based on the assigned retail client scenario for Tlou Furniture & Appliances (Rustenburg).

## Project Overview

| | |
|-|-|
| **Project ID** | CMPG325-2026-017 |
| **Client ID** | CLI-017 |
| **Assigned Organisation** | Tlou Furniture & Appliances (Rustenburg) |
| **Industry** | Retail |
| **Addressing Block** | 172.30.2.0/23 |
| **Assigned Feature** | Wireless Security - WPA2-PSK hardening |
| **Change Request** | CR6 - future branch office accommodation |

## Phase 2 Status

**Phase 2 implementation completed and tested.**

The working Packet Tracer network includes VLAN segmentation, inter-VLAN routing, DHCP, server connectivity, WPA2-PSK wireless security, routing/NAT, ISP simulation, and end-to-end connectivity testing.

## Implemented Topology

- ISR4321 router as **R1**
- ISR4321 router as simulated **ISP**
- Catalyst 3560 multilayer switch as **CORE-SW**
- Catalyst 2960 switches: **SW-ADMIN**, **SW-SALES**, **SW-WAREHOUSE**
- Access points: **AP1**, **AP2**
- **SERVER1**
- 3 Admin PCs, 4 Sales/POS PCs, 2 Warehouse PCs
- **STAFF-LAPTOP1**

## VLAN and Addressing Plan

| VLAN | Purpose | Network | Gateway |
|---|---|---|---|
| 10 | Admin / Management | 172.30.2.64/27 | 172.30.2.65 |
| 20 | Sales / POS | 172.30.2.0/26 | 172.30.2.1 |
| 30 | Warehouse / Inventory | 172.30.2.96/27 | 172.30.2.97 |
| 40 | Staff Wireless | 172.30.2.128/27 | 172.30.2.129 |
| 50 | Servers | 172.30.2.176/29 | 172.30.2.177 |
| 99 | Network Management | 172.30.2.160/28 | 172.30.2.161 |

Additional routed links:
- CORE-SW ↔ R1: 172.30.2.188/30 (.190 / .189)
- R1 ↔ ISP: 172.30.2.184/30 (.185 / .186)

> Note: VLAN 50 was used for the server segment because the Phase 1 document specified the server subnet but did not assign a VLAN number.

## Implemented Features

- 802.1Q trunks between CORE-SW and access switches
- Native VLAN 99 on switch-to-switch trunks
- Layer 3 inter-VLAN routing
- DHCP for Admin, Sales/POS, Warehouse and Staff Wi-Fi
- Static SERVER1 addressing
- WPA2-PSK with AES
- SSID: `Tlou-Staff-WiFi`
- Static routing on R1
- NAT/PAT overload
- Simulated ISP connectivity
- Successful end-to-end ping testing

## Testing Results

Successful tests included:
- Admin DHCP addressing
- Sales/POS DHCP addressing
- Warehouse DHCP addressing
- Inter-VLAN connectivity
- SERVER1 reachability
- Wireless gateway reachability
- Wireless-to-server reachability
- ISP reachability
- Simulated Internet ping to `8.8.8.8`

Recorded final tests showed **0% packet loss**.

## Repository Structure

```text
.
├── README.md
├── reflection.md
├── design/
├── packet-tracer/
├── documentation/
├── evidence/
└── troubleshooting/
```

The final `.pkt` file should be placed in `packet-tracer/`.
