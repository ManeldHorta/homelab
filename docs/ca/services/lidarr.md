# Lidarr

## Descripció

Lidarr és el servei del Media Stack encarregat de gestionar la música.

## Funcions

- Cerca de música
- Gestió de descàrregues
- Integració amb qBittorrent
- Organització de la biblioteca musical

## Emmagatzematge

La biblioteca musical utilitza:

`D:\media\music`

Dins del container, la root de la biblioteca és:

`/media/music`

qBittorrent exposa la biblioteca corresponent com:

`/music`

## Flux

Lidarr → indexadors → qBittorrent → descàrrega → organització → biblioteca

## Tdarr

Tdarr no processa la música.

## Integració

Lidarr treballa conjuntament amb:

- Prowlarr
- Jackett
- qBittorrent
- Navidrome

## Estat

Lidarr forma part del Media Stack que s'executa a PCVR1.
