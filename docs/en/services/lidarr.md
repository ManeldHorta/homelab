# Lidarr

## Description

Lidarr is the Media Stack service responsible for managing music.

## Functions

- Music search
- Download management
- qBittorrent integration
- Music library organization

## Storage

The music library uses:

`D:\media\music`

Inside the container, the library root is:

`/media/music`

qBittorrent exposes the corresponding library as:

`/music`

## Workflow

Lidarr → indexers → qBittorrent → download → organization → library

## Tdarr

Tdarr does not process music.

## Integration

Lidarr works together with:

- Prowlarr
- Jackett
- qBittorrent
- Navidrome

## Status

Lidarr is part of the Media Stack running on PCVR1.
