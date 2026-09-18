# Media Stack

## Description

The Media Stack is the collection of services responsible for managing, downloading, classifying and organizing multimedia content in the homelab.

It currently runs on PCVR1 using Docker.

## Components

- qBittorrent
- Radarr
- Sonarr
- Lidarr
- Prowlarr
- Jackett

## General Workflow

Search → Download → Organization → Processing → Library

Radarr, Sonarr and Lidarr manage their respective content and use qBittorrent for downloads. Prowlarr and Jackett provide indexer integration.

Video files may subsequently be processed by Tdarr.

## Storage

The main Windows paths are:

- `D:\media\downloads`
- `D:\media\movies`
- `D:\media\series`
- `D:\media\music`
- `D:\media\torrents`
- `D:\media\incomplete`

## Activation Policy

PCVR1 is a gaming computer that also hosts services. To avoid interfering with gaming, Media Stack download services:

- are started on demand;
- or are started automatically between 00:00 and 07:30.

Other Media Stack services are documented according to their specific role.

## Integration

Content managed by the Media Stack is primarily consumed or managed by:

- Jellyfin
- Navidrome
- Komga

Tdarr is part of the video processing workflow but is documented as a separate service.

## Status

The Media Stack currently runs on PCVR1 inside Docker.
