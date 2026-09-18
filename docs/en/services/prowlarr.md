# Prowlarr

## Description

Prowlarr centralizes management of indexers used by the Media Stack *arr services.

## Function

Prowlarr acts as the central configuration and integration point for indexers.

The services using this integration include:

- Radarr
- Sonarr
- Lidarr

## Architecture

Prowlarr → indexers → Radarr / Sonarr / Lidarr → qBittorrent

## Status

Prowlarr runs as part of the PCVR1 Media Stack inside Docker.

Indexer credentials and sensitive configuration are not documented here.
