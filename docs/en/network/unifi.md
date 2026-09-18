# UniFi

## Purpose

The local network infrastructure is managed using UniFi equipment.

## Current components

- USW Flex 2.5G 8 PoE — main switch.
- USW Flex 2.5G 5 — secondary switch.
- U7 Pro — Wi-Fi access point.
- U7 Lite — Wi-Fi access point.

## Physical topology

Livebox FIBRA
      │
      ▼
USW Flex 2.5G 8 PoE
 ├── U7 Pro
 ├── U7 Lite
 ├── USW Flex 2.5G 5
 ├── Mac Mini
 └── PCVR1

USW Flex 2.5G 5
 ├── PCVR2
 └── TV

## Main links

- USW Flex 2.5G 8 PoE → USW Flex 2.5G 5: 2.5 GbE.
- PCVR1 → main switch: 5 GbE.
- Mac Mini → main switch: 2.5 GbE.
- PCVR2 → secondary switch: 2.5 GbE.
- TV → secondary switch: Fast Ethernet.
- Both access points are connected to the main switch and receive PoE power.

## STP

UniFi shows STP active on the link between the two switches.

## Recovery

Detailed infrastructure information —IP addresses, MAC addresses, firmware, and other operational parameters— will be kept in the private recovery repository.
