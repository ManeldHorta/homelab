# Media Stack

## Descripció

El Media Stack és el conjunt de serveis encarregats de la gestió, descàrrega, classificació i organització del contingut multimèdia del homelab.

Actualment s'executa a PCVR1 mitjançant Docker.

## Components

- qBittorrent
- Radarr
- Sonarr
- Lidarr
- Prowlarr
- Jackett

## Flux general

Cerca → Descàrrega → Organització → Processament → Biblioteca

Radarr, Sonarr i Lidarr gestionen el contingut corresponent i utilitzen qBittorrent per a les descàrregues. Prowlarr i Jackett proporcionen integració amb indexadors.

Els fitxers de vídeo poden passar posteriorment per Tdarr per al processament.

## Emmagatzematge

Les principals rutes de Windows són:

- `D:\media\downloads`
- `D:\media\movies`
- `D:\media\series`
- `D:\media\music`
- `D:\media\torrents`
- `D:\media\incomplete`

## Política d'activació

PCVR1 és un equip de gaming que també allotja serveis. Per evitar interferències amb el gaming, els serveis de descàrrega del Media Stack:

- s'encenen a demanda;
- o s'encenen automàticament entre les 00:00 i les 07:30.

La resta de serveis del Media Stack es documenten segons la seva funció específica.

## Integració

Els continguts gestionats pel Media Stack són consumits o gestionats principalment per:

- Jellyfin
- Navidrome
- Komga

Tdarr forma part del flux de processament de vídeo, però es documenta com a servei independent.

## Estat

El Media Stack funciona actualment a PCVR1 dins de Docker.
