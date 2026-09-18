# qBittorrent

## Description

qBittorrent is the BitTorrent client used by the Media Stack to manage downloads.

It runs inside Docker on PCVR1.

## Container

- Container: `qbittorrent`
- Image: `linuxserver/qbittorrent`
- WebUI: port `8090`

## Volumes

- `D:\qbittorrent_config:/config`
- `D:\media\movies:/movies`
- `D:\media\series:/series`
- `D:\media\music:/music`
- `D:\media\downloads:/downloads`
- `D:\media\torrents:/watch`
- `D:\media\incomplete:/incomplete`

## Downloads

Incomplete downloads use:

`D:\media\incomplete`

Documented working folders include:

- `D:\media\incomplete\lidarr`
- `D:\media\incomplete\movies`
- `D:\media\incomplete\series`

Completed content arrives in:

`D:\media\downloads`

## Integration

qBittorrent is used by:

- Radarr
- Sonarr
- Lidarr

## Activation Policy

PCVR1 download services do not run permanently. qBittorrent is activated on demand or during the 00:00–07:30 night-time window.

## Telegram

Telegram integration was configured through qBittorrent External Program.

The script works when executed manually inside the container, but the External Program trigger is not reliably executing with the current configuration.

This issue is intentionally left unchanged and qBittorrent has not been downgraded.

Telegram tokens and credentials are not documented.
