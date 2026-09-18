# Radarr

## Descripció

Radarr és el servei del Media Stack encarregat de gestionar les pel·lícules.

## Funcions

- Cerca de pel·lícules
- Gestió de descàrregues
- Integració amb qBittorrent
- Organització de la biblioteca de pel·lícules

## Emmagatzematge

La biblioteca de pel·lícules utilitza:

`D:\media\movies`

Dins del container, la root de la biblioteca és:

`/media/movies`

qBittorrent exposa la biblioteca corresponent com:

`/movies`

## Flux

Radarr → indexadors → qBittorrent → descàrrega → organització → biblioteca → Tdarr

## Integració

Radarr treballa conjuntament amb:

- Prowlarr
- Jackett
- qBittorrent
- Tdarr
- Jellyfin

## Estat

Radarr forma part del Media Stack que s'executa a PCVR1.
