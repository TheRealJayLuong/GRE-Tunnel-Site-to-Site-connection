# GRE-Tunnel-Site-to-Site-connection

## Network Topology Documentation

Overview

This topology showcases a sophisticated and secure Layer 2 and Layer 3 network design integrating the following technologies:

Dynamic Trunking Protocol (DTP)

VLAN Trunking Protocol (VTP)

Hot Standby Router Protocol (HSRP)

Port Security

Open Shortest Path First (OSPF)

GRE Tunnel

The setup supports redundancy, segmentation, dynamic routing, and remote connectivity.

## VLAN Design

VLAN Purpose	Subnet	Color-Coded Devices

10	General Access	192.168.10.0/24	PC0, PC1 (Yellow)

20	Staff	192.168.20.0/24	PC2, PC3 (Blue)

30	Secure Zone	192.168.30.0/24	PC4, PC5 (Green)

40	Infrastructure	192.168.40.0/24	Switch MGMT

VTP Domain: VLANs centrally managed across switches using VTP (likely VTP Server on SW and Client on DSW).

DTP: Enabled to dynamically negotiate trunk links between switches.

## High Availability

HSRP

SW (Active) and DSW (Standby) for VLANs 10, 20, and 30.

Each VLAN has its own virtual IP, facilitating seamless failover.

VLAN	Virtual IP	

10	192.168.10.100	

20	192.168.20.100	

30	192.168.30.100	

DSW01 mode Active

DSW02 mode Standby

## Security

Port Security

Configured on access ports to limit MAC address learning and prevent unauthorized device access.

Violation mode: Protect mode with sticky MAC address technique


## Routing and Connectivity

Area 0 is used for backbone OSPF routing.

Enables dynamic routing between routers, switches and internal networks.

## GRE Tunnel

Tunnel between R1 and R2

Tunnel IP: 172.168.20.0/24

## Lab Use Case

Design and evaluate a scalable enterprise network featuring:

Secure segmented access via VLANs.

Redundant gateway infrastructure using HSRP.

Centralized VLAN management via VTP.

Dynamic trunking negotiation with DTP.

Port-level security against unauthorized devices.

Dynamic routing with OSPF.

Inter-site traffic encapsulation using GRE Tunnel.