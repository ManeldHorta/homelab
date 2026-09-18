# Sonarr

## Descripció

Sonarr és el servei del Media Stack encarregat de gestionar les sèries de televisió.

## Funcions

- Cerca de sèries i episodis
- Gestió de descàrregues
- Integració amb qBittorrent
- Organització de les sèries

## Emmagatzematge

La biblioteca de sèries utilitza:

`D:\media\series`

Dins del container, la root de la biblioteca és:

`/media/series`

qBittorrent exposa la biblioteca corresponent com:

`/series`

El directori de descàrregues és visible a Sonarr com:

`/downloads`

## Flux

Sonarr → indexadors → qBittorrent → descàrrega → organització → biblioteca → Tdarr

## Integració

Sonarr treballa conjuntament amb:

- Prowlarr
- Jackett
- qBittorrent
- Tdarr
- Jellyfin

## Estat

Sonarr forma part del Media Stack que s'executa a PCVR1.
