# Homelab Overview

## Current Physical Infrastructure

The homelab currently consists of three physical systems:

| Host | Role |
|---|---|
| Mac Mini | Docker host running Zabbix |
| PCVR1 | Main Docker host: UniFi OS, Media Stack, Tdarr and Local AI |
| PCVR2 | Third physical homelab system |

## High-Level Architecture

Internet
  |
Orange / Livebox
  |
Homelab Network
  |
  +----------------+----------------+----------------+
  |                |                |
Mac Mini         PCVR1            PCVR2
  |                |                |
Docker           Docker
Zabbix           UniFi OS
                 Media Stack
                 Tdarr
                 Local AI

## Mac Mini

The Mac Mini is one of the three physical systems in the homelab.

Its current role is to host Docker and run Zabbix.

UniFi OS was previously hosted on the Mac Mini, but was moved to PCVR1 because the Mac Mini has limited local storage capacity.

## PCVR1

PCVR1 is currently the main workload host in the homelab.

Docker workloads running on PCVR1 include:

- UniFi OS
- Media Stack
- Tdarr
- Local AI

### Media Stack

The Media Stack includes:

- qBittorrent
- Radarr
- Sonarr
- Lidarr
- Prowlarr
- Jackett

Media services include:

- Jellyfin
- Navidrome
- Komga
- Dashy

Tdarr also runs on PCVR1 and uses the PCVR1 GPU node for video processing.

### Local AI

The Local AI environment runs inside Docker on PCVR1.

The documented components include:

- Ollama
- Open WebUI
- ComfyUI
- Coqui TTS
- Piper
- Presenton
- ACE-Step

The Local AI environment is intentionally kept local and is designed to operate without sending data to external AI services.

## PCVR2

PCVR2 is the third physical system in the homelab.

The services currently running on PCVR2 are not detailed in this document yet.

A detailed inventory of PCVR2 will be documented later once its current configuration has been reviewed.

## Current Architecture and Future Expansion

This document describes only the current operational state of the homelab.

Future infrastructure changes are not considered part of the current architecture until they have actually been implemented.

The planned migration of the Media Stack, Jellyfin, Navidrome and Komga to a Synology NAS is not included in this document because it has not yet been implemented.