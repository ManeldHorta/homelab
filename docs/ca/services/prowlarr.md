# Prowlarr

## Descripció

Prowlarr centralitza la gestió dels indexadors utilitzats pels serveis *arr del Media Stack.

## Funció

Prowlarr actua com a punt central de configuració i integració dels indexadors.

Els serveis que utilitzen aquesta integració inclouen:

- Radarr
- Sonarr
- Lidarr

## Arquitectura

Prowlarr → indexadors → Radarr / Sonarr / Lidarr → qBittorrent

## Estat

Prowlarr s'executa com a part del Media Stack de PCVR1 dins de Docker.

No es documenten aquí credencials ni configuracions sensibles dels indexadors.
