# Sonarr

## Description

Sonarr is the Media Stack service responsible for managing TV series.

## Functions

- Series and episode search
- Download management
- qBittorrent integration
- Series organization

## Storage

The series library uses:

`D:\media\series`

Inside the container, the library root is:

`/media/series`

qBittorrent exposes the corresponding library as:

`/series`

The download directory is visible to Sonarr as:

`/downloads`

## Workflow

Sonarr → indexers → qBittorrent → download → organization → library → Tdarr

## Integration

Sonarr works together with:

- Prowlarr
- Jackett
- qBittorrent
- Tdarr
- Jellyfin

## Status

Sonarr is part of the Media Stack running on PCVR1.
