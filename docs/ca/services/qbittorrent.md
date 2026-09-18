# qBittorrent

## Descripció

qBittorrent és el client BitTorrent utilitzat pel Media Stack per gestionar les descàrregues.

S'executa dins de Docker a PCVR1.

## Container

- Container: `qbittorrent`
- Imatge: `linuxserver/qbittorrent`
- WebUI: port `8090`

## Volums

- `D:\qbittorrent_config:/config`
- `D:\media\movies:/movies`
- `D:\media\series:/series`
- `D:\media\music:/music`
- `D:\media\downloads:/downloads`
- `D:\media\torrents:/watch`
- `D:\media\incomplete:/incomplete`

## Descàrregues

Les descàrregues incompletes utilitzen:

`D:\media\incomplete`

Les carpetes de treball documentades inclouen:

- `D:\media\incomplete\lidarr`
- `D:\media\incomplete\movies`
- `D:\media\incomplete\series`

Els continguts acabats arriben a:

`D:\media\downloads`

## Integració

qBittorrent és utilitzat per:

- Radarr
- Sonarr
- Lidarr

## Política d'activació

Els serveis de descàrrega de PCVR1 no funcionen permanentment. qBittorrent s'activa a demanda o dins de la franja nocturna de 00:00 a 07:30.

## Telegram

Es va configurar una integració amb Telegram mitjançant External Program d'qBittorrent.

El script funciona quan s'executa manualment dins del container, però el trigger d'External Program no s'està executant de manera fiable amb la configuració actual.

Aquesta incidència no es modifica actualment i no s'ha fet downgrade de qBittorrent.

No es documenten tokens ni credencials de Telegram.
