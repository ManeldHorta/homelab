# Tdarr

## Descripció

Tdarr és el sistema de processament i conversió de vídeo del homelab.

S'executa a PCVR1 i utilitza la GPU NVIDIA RTX 4080 per al processament.

## Versió i node

- Tdarr: `2.87.01`
- Node: `PCVR1`
- GPU: NVIDIA GeForce RTX 4080
- GPU workers: `4`

Quatre GPU workers és la configuració validada com a estable. No s'ha de modificar sense una raó concreta.

## Objectiu

L'objectiu és mantenir la biblioteca de vídeo en H.265/HEVC.

- Els fitxers ja en HEVC no es recodifiquen a HEVC.
- Els fitxers amb altres còdecs de vídeo es poden convertir a HEVC amb NVIDIA NVENC.
- El contenidor preferit és MKV.
- La música no és processada per Tdarr.

## Flow

Input File
→ Run Classic Transcode Plugin
→ Replace Original File
→ Send Web Request

La notificació de Telegram es produeix després del processament i substitució correcta del fitxer.

## Plugin local

`Tdarr_Plugin_Local_HEVC_CAT_AudioSubs`

Ruta Windows:

`D:\docker\tdarr\server\Tdarr\Plugins\Local`

Ruta dins del container:

`/app/server/Tdarr/Plugins/Local`

El plugin:

- manté el vídeo HEVC sense recodificar;
- converteix vídeo no-HEVC amb `hevc_nvenc`;
- conserva l'àudio original;
- conserva una pista preferida en català o, si no existeix, espanyol;
- selecciona els subtítols segons català → espanyol → anglès;
- si no hi ha cap subtítol preferit, manté els subtítols existents.

## Regles d'àudio

Es manté sempre l'àudio original.

A més, es conserva una única pista preferida:

1. Català
2. Espanyol
3. Si no existeix cap de les dues, només l'original

La qualitat d'àudio es prioritza segons el ranking definit al plugin.

## Regles de subtítols

La preferència és:

1. Català
2. Espanyol
3. Anglès

Si hi ha diverses pistes de la llengua escollida, es prioritzen els formats ASS/SSA, després SRT i després altres formats.

Si no existeix cap subtítol preferit, es mantenen els subtítols existents.

## Docker

Els volums principals són:

- `D:/docker/tdarr/server:/app/server`
- `D:/docker/tdarr/configs:/app/configs`
- `D:/docker/tdarr/logs:/app/logs`
- `D:/cache:/temp`
- `D:/Media:/media`

El Node també té accés a `/media` i `/temp`.

## Cache

El Transcode Cache utilitza:

`/temp`

No s'utilitza el workDir intern anterior com a cache de transcodificació.

## Telegram

Tdarr envia una notificació mitjançant un Web Request després del `Replace Original File`.

La configuració utilitza una variable privada per al token de Telegram.

No s'inclouen tokens ni credencials al repositori públic.

## Estat

Tdarr funciona actualment de manera estable amb quatre GPU workers.

El pipeline de vídeo està operatiu per a pel·lícules i sèries.
