# Radarr

## Description

Radarr is the Media Stack service responsible for managing movies.

## Functions

- Movie search
- Download management
- qBittorrent integration
- Movie library organization

## Storage

The movie library uses:

`D:\media\movies`

Inside the container, the library root is:

`/media/movies`

qBittorrent exposes the corresponding library as:

`/movies`

## Workflow

Radarr → indexers → qBittorrent → download → organization → library → Tdarr

## Integration

Radarr works together with:

- Prowlarr
- Jackett
- qBittorrent
- Tdarr
- Jellyfin

## Status

Radarr is part of the Media Stack running on PCVR1.
