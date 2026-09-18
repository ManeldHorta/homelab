# Tdarr

## Description

Tdarr is the homelab's video processing and conversion system.

It runs on PCVR1 and uses an NVIDIA GeForce RTX 4080 GPU for processing.

## Version and Node

- Tdarr: `2.87.01`
- Node: `PCVR1`
- GPU: NVIDIA GeForce RTX 4080
- GPU workers: `4`

Four GPU workers is the validated stable configuration. It should not be changed without a specific reason.

## Objective

The goal is to keep the video library in H.265/HEVC.

- Files already using HEVC are not re-encoded to HEVC.
- Files using other video codecs may be converted to HEVC using NVIDIA NVENC.
- MKV is the preferred container.
- Music is not processed by Tdarr.

## Flow

Input File
→ Run Classic Transcode Plugin
→ Replace Original File
→ Send Web Request

The Telegram notification is sent after successful processing and replacement of the file.

## Local Plugin

`Tdarr_Plugin_Local_HEVC_CAT_AudioSubs`

Windows path:

`D:\docker\tdarr\server\Tdarr\Plugins\Local`

Container path:

`/app/server/Tdarr/Plugins/Local`

The plugin:

- keeps HEVC video without re-encoding;
- converts non-HEVC video using `hevc_nvenc`;
- keeps the original audio;
- keeps one preferred Catalan or, if unavailable, Spanish audio track;
- selects subtitles using Catalan → Spanish → English;
- if no preferred subtitle exists, keeps the existing subtitles.

## Audio Rules

The original audio track is always retained.

In addition, one preferred track is kept:

1. Catalan
2. Spanish
3. If neither exists, only the original

Audio quality is prioritized according to the ranking defined in the plugin.

## Subtitle Rules

The preference is:

1. Catalan
2. Spanish
3. English

When multiple tracks exist for the selected language, ASS/SSA is preferred, followed by SRT and then other formats.

If no preferred subtitle exists, existing subtitles are retained.

## Docker

Main volumes are:

- `D:/docker/tdarr/server:/app/server`
- `D:/docker/tdarr/configs:/app/configs`
- `D:/docker/tdarr/logs:/app/logs`
- `D:/cache:/temp`
- `D:/Media:/media`

The Node also has access to `/media` and `/temp`.

## Cache

The Transcode Cache uses:

`/temp`

The previous internal work directory is not used as the transcoding cache.

## Telegram

Tdarr sends a notification using a Web Request after `Replace Original File`.

The configuration uses a private variable for the Telegram token.

Tokens and credentials are not included in the public repository.

## Status

Tdarr currently operates stably with four GPU workers.

The video processing pipeline is operational for movies and series.
