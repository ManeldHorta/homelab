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
