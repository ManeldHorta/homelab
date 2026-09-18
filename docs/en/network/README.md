# Network

## Overview

The homelab network provides connectivity between the Internet, physical systems, Docker services and client devices.

The infrastructure uses UniFi equipment, and UniFi OS is currently managed from PCVR1.

## Internet connection

Internet connectivity is provided through Orange and the Livebox.

The detailed operator-specific connection parameters will be documented here once they are consolidated.

## UniFi

UniFi OS currently runs on PCVR1.

The UniFi infrastructure is responsible for network management and UniFi device administration.

## Homelab systems

The main physical systems connected to the network are:

- Mac Mini
- PCVR1
- PCVR2

PCVR1 hosts the main Docker services of the homelab.

## VLANs

Network segmentation using VLANs is part of the homelab network design.

Detailed VLAN, subnet, DHCP, DNS and firewall configuration will be documented once validated.

## Wi-Fi

The Wi-Fi infrastructure uses UniFi access points.

Wi-Fi networks, VLAN assignments and detailed configuration will be documented in this section.

## Specialized networks

The homelab includes dedicated networks for IoT devices and virtual-reality devices.

The final configuration and inter-network access rules will be documented once consolidated.

## Network security

Firewall configuration and access rules between networks will be documented separately from credentials and other sensitive information.
