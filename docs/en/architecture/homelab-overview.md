# Homelab Architecture

## Overview

The homelab is a home infrastructure focused on services, automation, media, monitoring, and technology experimentation.

The current architecture combines several physical systems, a UniFi network infrastructure, and services mainly deployed with Docker.

The architecture is documented by clearly separating the current state from planned future changes.

## Physical systems

### PCVR1

PCVR1 is the main homelab system and is also a gaming computer.

It currently hosts a large part of the Docker services:

- UniFi OS;
- Media Stack;
- Tdarr;
- Local AI;
- Portainer;
- other supporting services.

The system has an NVIDIA RTX 4080 GPU used for Tdarr processing and for local AI workloads when active.

Gaming has priority over homelab workloads. For this reason, some services run only on demand or within controlled time windows.

### Mac Mini

The Mac Mini is a second Docker host in the infrastructure.

Zabbix currently runs on it for monitoring.

Its role is independent from PCVR1 and allows monitoring to remain separate from the main service system.

### PCVR2

PCVR2 is a second gaming computer connected to the local network.

It currently does not host homelab services.

## Network

The current network uses a home gateway and UniFi infrastructure.

The UniFi infrastructure includes:

- a USW Flex 2.5G 8 PoE main switch;
- a USW Flex 2.5G 5 secondary switch;
- a U7 Pro;
- a U7 Lite.

The main systems are connected to the switching infrastructure using Ethernet.

The Wi-Fi network currently uses different SSIDs according to usage:

- `PCVR`: gaming and virtual reality;
- `Dispositius`: computers, mobile devices, and general-purpose devices;
- `IoT`: smart-home and other IoT devices.

These SSIDs are not 802.1Q VLANs. Real VLAN-based segmentation is part of the future architecture.

Specific network documentation is available under `docs/en/network/`.

## Service platform

Most services run using Docker.

Deployments are separated into different Compose projects according to their function.

The main service areas are:

### Media Stack

Includes services related to media management and downloading, such as:

- qBittorrent;
- Sonarr;
- Radarr;
- Lidarr;
- Prowlarr;
- Jackett.

### Media services

Current media services include:

- Jellyfin;
- Navidrome;
- Komga.

These services use the main system's media storage structure.

### Media processing

Tdarr is used to process and convert media content.

Video conversion is focused on H.265/HEVC and uses NVIDIA GPU acceleration.

Tdarr has a processing node associated with PCVR1.

### Local artificial intelligence

PCVR1 hosts a local AI stack deployed with Docker.

It includes tools for:

- AI models;
- image generation;
- voice generation;
- text-to-speech;
- presentations;
- music generation;
- web interfaces.

The AI stack is started on demand and is not part of the permanent system workload.

### Monitoring

Zabbix is used to monitor the infrastructure.

The Zabbix server currently runs on the Mac Mini.

### Administration

Portainer is used to simplify Docker container administration.

## Storage

PCVR1 currently has a single data disk D: of approximately 8 TB.

The main media data structure is:

```text
D:\media\downloads
D:\media\music
D:\media\movies
D:\media\tv
```

Tdarr also uses separate temporary space for processing.

There is currently no independent local backup infrastructure. The backup and data-protection strategy will be defined as part of the planned migration to a Synology NAS.

## Remote access

Remote access to current services is managed using Tailscale.

The specific mechanism is documented in:

`docs/en/network/remote-access.md`

Detailed configuration is not part of this architecture document.

## Operations

The infrastructure is designed around the fact that PCVR1 is also a gaming computer.

The priority is:

1. interactive use and gaming;
2. required services;
3. media processing and other non-interactive workloads.

Media Stack and Tdarr normally operate within a 00:00–07:30 window.

The local AI stack is started only when required.

Operational automation is documented under `docs/en/operations/`.

## Future architecture

The planned architectural evolution includes:

- replacing the current gateway with a dedicated router/firewall;
- implementing real 802.1Q VLANs;
- segmenting devices and services;
- firewall rules between networks;
- progressively replacing Tailscale with a router-managed VPN;
- migrating media services to a Synology NAS;
- implementing a backup strategy associated with the new storage system.

These changes are future objectives and are not part of the current infrastructure state.
