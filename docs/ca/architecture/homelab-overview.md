# Arquitectura del homelab

## Visió general

El homelab és una infraestructura domèstica orientada a serveis, automatització, multimèdia, monitorització i proves tecnològiques.

L'arquitectura actual combina diversos sistemes físics, una infraestructura de xarxa UniFi i serveis desplegats principalment amb Docker.

L'arquitectura es documenta separant sempre l'estat actual de les evolucions previstes.

## Sistemes físics

### PCVR1

PCVR1 és el sistema principal del homelab i també un ordinador de gaming.

Actualment concentra bona part dels serveis Docker:

- UniFi OS;
- Media Stack;
- Tdarr;
- Local AI;
- Portainer;
- altres serveis auxiliars.

El sistema disposa d'una GPU NVIDIA RTX 4080 utilitzada per a les tasques de processament de Tdarr i per a les càrregues d'IA local quan aquestes estan actives.

El gaming té prioritat sobre les càrregues del homelab. Per aquest motiu, alguns serveis s'executen només sota demanda o dins de finestres horàries controlades.

### Mac Mini

El Mac Mini és un segon host Docker de la infraestructura.

Actualment s'hi executa Zabbix per a la monitorització.

La seva funció és independent de PCVR1 i permet mantenir la monitorització separada del sistema principal de serveis.

### PCVR2

PCVR2 és un segon ordinador de gaming connectat a la xarxa local.

Actualment no allotja serveis del homelab.

## Xarxa

La xarxa actual utilitza un gateway domèstic i infraestructura UniFi.

La infraestructura UniFi inclou:

- un switch principal USW Flex 2.5G 8 PoE;
- un switch secundari USW Flex 2.5G 5;
- un U7 Pro;
- un U7 Lite.

Els equips principals es connecten a la infraestructura de commutació mitjançant Ethernet.

La xarxa Wi-Fi utilitza actualment diferents SSID segons el tipus d'ús:

- `PCVR`: gaming i realitat virtual;
- `Dispositius`: ordinadors, mòbils i dispositius d'ús general;
- `IoT`: dispositius domòtics i altres dispositius IoT.

Aquests SSID no són VLANs 802.1Q. La segmentació real mitjançant VLANs forma part de l'arquitectura futura.

La documentació específica de xarxa es troba a `docs/ca/network/`.

## Plataforma de serveis

La major part dels serveis s'executen amb Docker.

Els desplegaments estan separats en diferents projectes Compose segons la seva funció.

Les principals àrees de servei són:

### Media Stack

Inclou els serveis relacionats amb la gestió i descàrrega de contingut multimèdia, com ara:

- qBittorrent;
- Sonarr;
- Radarr;
- Lidarr;
- Prowlarr;
- Jackett.

### Multimèdia

Els serveis multimèdia actuals inclouen:

- Jellyfin;
- Navidrome;
- Komga.

Aquests serveis utilitzen l'estructura d'emmagatzematge multimèdia del sistema principal.

### Processament multimèdia

Tdarr s'utilitza per processar i convertir contingut multimèdia.

La conversió de vídeo està orientada a H.265/HEVC i utilitza acceleració GPU NVIDIA.

Tdarr disposa d'un node de processament associat a PCVR1.

### Intel·ligència artificial local

PCVR1 disposa d'un stack d'IA local desplegat amb Docker.

Inclou eines per a:

- models d'IA;
- generació d'imatges;
- generació de veu;
- text-to-speech;
- presentacions;
- generació musical;
- interfície web.

El stack d'IA s'activa sota demanda i no forma part de la càrrega permanent del sistema.

### Monitorització

Zabbix s'utilitza per monitoritzar la infraestructura.

Actualment el servidor Zabbix s'executa al Mac Mini.

### Administració

Portainer s'utilitza per facilitar l'administració dels contenidors Docker.

## Emmagatzematge

Actualment PCVR1 disposa d'un únic disc de dades D: d'aproximadament 8 TB.

L'estructura principal de dades multimèdia és:

```text
D:\media\downloads
D:\media\music
D:\media\movies
D:\media\tv
```

Tdarr utilitza també espai temporal separat per al processament.

Actualment no hi ha una infraestructura de còpia de seguretat local independent. L'estratègia de còpies de seguretat i protecció de dades es definirà en el futur amb la migració prevista a un NAS Synology.

## Accés remot

L'accés remot actual als serveis es gestiona mitjançant Tailscale.

La descripció específica d'aquest mecanisme es troba a:

`docs/ca/network/remote-access.md`

La configuració detallada no forma part d'aquest document d'arquitectura.

## Operacions

La infraestructura està dissenyada tenint en compte que PCVR1 és també un ordinador de gaming.

La prioritat és:

1. ús interactiu i gaming;
2. serveis necessaris;
3. processament multimèdia i altres càrregues no interactives.

El Media Stack i Tdarr disposen d'una finestra operativa habitual entre les 00:00 i les 07:30.

El stack d'IA local s'activa només quan és necessari.

L'automatització operativa es documenta a `docs/ca/operations/`.

## Arquitectura futura

L'evolució prevista de l'arquitectura inclou:

- substitució del gateway actual per un router/firewall propi;
- implementació de VLANs 802.1Q reals;
- segmentació de dispositius i serveis;
- regles de firewall entre xarxes;
- substitució progressiva de Tailscale per una VPN gestionada pel router;
- migració dels serveis multimèdia a un NAS Synology;
- implementació d'una estratègia de còpies de seguretat associada al nou sistema d'emmagatzematge.

Aquestes modificacions són objectius futurs i no formen part de l'estat actual de la infraestructura.
