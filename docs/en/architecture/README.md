# Homelab Architecture

## Overview

This homelab is a self-hosted infrastructure focused on local services, automation, media management and local artificial intelligence.

The infrastructure is organised around Docker containers and local compute and storage resources.

## Main Areas

- Infrastructure and container management
- Media management and processing
- Media consumption and content services
- Local artificial intelligence
- Monitoring and operations
- Storage and backup

## Docker Architecture

### Infrastructure

- Portainer â€” Docker management and administration

### Media Stack

- qBittorrent â€” download client
- Radarr â€” movie management
- Sonarr â€” TV series management
- Lidarr â€” music management
- Prowlarr â€” indexer management
- Jackett â€” indexer integration
- Tdarr â€” media processing and video transcoding

### Media Services

- Jellyfin â€” video and media playback
- Navidrome â€” music server
- Komga â€” comics and digital reading
- Dashy â€” self-hosted service dashboard

### Local AI

- Ollama â€” local language model runtime
- Open WebUI â€” web interface for local AI
- ComfyUI â€” image generation and AI workflows
- Coqui TTS â€” text-to-speech
- Piper â€” text-to-speech
- Presenton â€” AI-assisted presentation generation
- ACE-Step â€” local music generation

## Media Data Flow

```text
                    Download
                       |
                       v
                  qBittorrent
                       |
             +---------+---------+
             |                   |
             v                   v
           Radarr              Sonarr
             |                   |
             +---------+---------+
                       |
                       v
                Media libraries
                       |
                       v
                     Tdarr
                       |
                       v
                  H.265 / HEVC
                       |
                       v
                   Jellyfin

Lidarr manages the music workflow independently.

Music is stored separately and is not processed by the Tdarr video transcoding pipeline.

Navidrome provides access to the music library.

Komga provides access to the comics library.

Dashy provides a central dashboard for accessing self-hosted services.

Video Processing

Tdarr is used to standardise video content to H.265 / HEVC.

Files that are already encoded using HEVC are not unnecessarily re-encoded.

Non-HEVC video can be transcoded using NVIDIA NVENC.

The Tdarr workflow also manages audio and subtitle streams according to the configured language and quality rules.

The current workflow uses a local Tdarr classic plugin and a Flow containing:

Input File
    |
    v
Run Classic Transcode Plugin
    |
    v
Replace Original File

The replacement step is required because the final processed file is initially created in the Tdarr transcode cache.

Local AI Architecture

The local AI environment is designed to keep AI processing inside the home infrastructure whenever practical.

Ollama provides local language-model execution.

Open WebUI provides a web interface for interacting with local AI models.

Additional services provide local image generation, speech synthesis, presentation generation and music generation.

                       Local AI
                          |
          +---------------+---------------+
          |               |               |
          v               v               v
       Ollama          ComfyUI       Open WebUI
          |               |               |
          +---------------+---------------+
                          |
                 Additional AI services
                 TTS / presentations / music
Container Management

Portainer provides central administration of the Docker environment.

Monitoring and Operations

Zabbix is used as the monitoring platform for the homelab infrastructure.

Automation is used for media acquisition, organisation, transcoding and notifications.

Telegram notifications are integrated into the media workflow for relevant download and transcoding events.

Security and Privacy

The infrastructure follows a local-first approach.

Services that do not require external access are intended to remain inside the local network.

This public repository must not contain:

Passwords
API keys
Access tokens
Bot tokens
Private certificates
Private keys
Other credentials

Sensitive configuration is maintained separately in the private homelab repository.

Documentation Status

The following areas still require a detailed infrastructure inventory:

Physical server hardware
Virtual machines
Network topology
Router and firewall configuration
UniFi infrastructure
VLAN configuration
Storage architecture
Backup strategy
Remote access
Detailed Docker volume mappings
Service dependencies
Monitoring architecture
