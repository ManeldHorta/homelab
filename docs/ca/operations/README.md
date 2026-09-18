# Operacions

## Visió general

Aquest apartat documenta els procediments operatius del homelab.

## Docker

Els serveis principals s'executen amb Docker.

PCVR1 és el principal host Docker i executa:

- UniFi OS
- Media Stack
- Tdarr
- Entorn d'IA local

El Mac Mini també executa Docker i allotja Zabbix.

## Media Stack

El Media Stack inclou serveis de descàrrega i gestió multimèdia.

Els serveis de descàrrega del Media Stack de PCVR1 no es mantenen necessàriament actius durant les sessions de gaming. Es poden activar a demanda o funcionar durant la franja nocturna de 00:00 a 07:30.

## Automatització operativa

El Media Stack de PCVR1 disposa d'automatitzacions gestionades mitjançant Windows Task Scheduler.

### Media Stack

El Media Stack s'inicia i s'atura automàticament segons la següent planificació:

- Arrencada: cada dia a les 00:00.
- Aturada: cada dia a les 07:30.

Les tasques programades utilitzen els scripts:

- `C:\scripts\start-mediastack.ps1`
- `C:\scripts\stop-mediastack.ps1`

El script d'arrencada:

1. Inicia Docker Desktop.
2. Espera fins que el dimoni de Docker respongui.
3. Inicia els contenidors del Media Stack.
4. Inicia Tdarr i el seu node.

El script d'aturada atura els contenidors del Media Stack i Tdarr.

### Tdarr Watchdog

Tdarr disposa d'un watchdog específic per al node GPU de PCVR1.

La tasca `TdarrNode-Watchdog` s'executa:

- cada 5 minuts;
- durant la franja de 00:00 a 07:30;
- mitjançant `C:\scripts\watch-tdarr-node.ps1`.

El watchdog revisa els logs recents de `tdarr-node` i detecta específicament els errors:

- `MODULE_NOT_FOUND`
- `Cannot find module`

Quan detecta un d'aquests errors:

1. Envia una notificació a Telegram.
2. Reinicia automàticament el contenidor `tdarr-node`.
3. Registra l'incident a `C:\scripts\tdarr-watch.log`.

El reinici es realitza directament mitjançant Docker i afecta únicament el contenidor `tdarr-node`.

El contenidor `tdarr-node` disposa addicionalment de la política Docker:

`restart: always`

Aquesta política proporciona un mecanisme addicional de recuperació del contenidor.

Les credencials i tokens de Telegram no formen part de la documentació pública.

## Tdarr

Tdarr s'utilitza per al processament de vídeo.

L'objectiu actual és convertir el vídeo a H.265 / HEVC per reduir la necessitat de transcodificació durant la reproducció.

Tdarr utilitza el node GPU de PCVR1 amb una NVIDIA RTX 4080 i la configuració estable actual utilitza quatre workers GPU.

## IA local

L'entorn d'IA local s'executa a PCVR1.

Els serveis d'IA només s'inicien quan són necessaris, de manera que el gaming manté prioritat sobre les càrregues del homelab.

## Monitorització

Zabbix s'executa dins de Docker al Mac Mini i s'utilitza per monitoritzar la infraestructura.

## Notificacions

El homelab utilitza Telegram per rebre notificacions d'esdeveniments operatius.

Les credencials i tokens de Telegram no formen part de la documentació pública.

## Actualitzacions

Les actualitzacions dels serveis Docker s'han de realitzar de manera controlada, comprovant abans l'estat del servei i després validant-ne el funcionament.

## Recuperació

Els procediments detallats de còpia de seguretat i recuperació s'incorporaran a mesura que es documenti la infraestructura de storage i backup.