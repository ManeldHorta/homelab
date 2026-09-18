# Visió general del Homelab

## Infraestructura física actual

Actualment el homelab està format per tres equips físics:

| Equip | Funció |
|---|---|
| Mac Mini | Host Docker amb Zabbix |
| PCVR1 | Host Docker principal: UniFi OS, Media Stack, Tdarr i IA local |
| PCVR2 | Tercer equip físic del homelab |

## Arquitectura general

Internet
  |
Orange / Livebox
  |
Xarxa del homelab
  |
  +----------------+----------------+----------------+
  |                |                |
Mac Mini         PCVR1            PCVR2
  |                |                |
Docker           Docker
Zabbix           UniFi OS
                 Media Stack
                 Tdarr
                 IA local

## Mac Mini

El Mac Mini és un dels tres equips físics del homelab.

La seva funció actual és allotjar Docker i executar Zabbix.

UniFi OS estava anteriorment allotjat al Mac Mini, però es va traslladar a PCVR1 perquè l'espai d'emmagatzematge del Mac Mini és limitat.

## PCVR1

PCVR1 és actualment el principal equip de càrrega de treball del homelab.

Hi funciona Docker amb:

- UniFi OS
- Media Stack
- Tdarr
- IA local

### Media Stack

El Media Stack inclou:

- qBittorrent
- Radarr
- Sonarr
- Lidarr
- Prowlarr
- Jackett

Els serveis multimèdia inclouen:

- Jellyfin
- Navidrome
- Komga
- Dashy

Tdarr també funciona a PCVR1 i utilitza el node GPU PCVR1 per al processament de vídeo.

### IA local

L'entorn d'IA local funciona dins de Docker a PCVR1.

Els components documentats inclouen:

- Ollama
- Open WebUI
- ComfyUI
- Coqui TTS
- Piper
- Presenton
- ACE-Step

L'entorn d'IA es manté local expressament i està destinat a funcionar sense enviar les dades a serveis d'IA externs.

## PCVR2

PCVR2 és el tercer equip físic del homelab.

En aquest document no es detallen encara els serveis que hi funcionen.

L'inventari detallat de PCVR2 es documentarà posteriorment, un cop revisada la seva configuració actual.

## Arquitectura actual i futures ampliacions

Aquest document descriu únicament l'estat operatiu actual del homelab.

Les futures modificacions de la infraestructura no es consideren part de l'arquitectura actual fins que s'hagin implantat.

La futura migració del Media Stack, Jellyfin, Navidrome i Komga a un NAS Synology no s'inclou en aquest document perquè encara no s'ha realitzat.