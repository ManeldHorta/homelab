# Operations

## Overview

This section documents the operational procedures for the homelab.

## Docker

The main services run using Docker.

PCVR1 is the primary Docker host and runs:

- UniFi OS
- Media Stack
- Tdarr
- Local AI environment

The Mac Mini also runs Docker and hosts Zabbix.

## Media Stack

The Media Stack includes download and media-management services.

PCVR1 download services are not necessarily kept running during gaming sessions. They can be started on demand or run during the 00:00–07:30 overnight window.

## Tdarr

Tdarr is used for video processing.

The current objective is to convert video to H.265 / HEVC to reduce the need for transcoding during playback.

Tdarr uses the PCVR1 GPU node with an NVIDIA RTX 4080, and the current stable configuration uses four GPU workers.

## Local AI

The local AI environment runs on PCVR1.

AI services are started only when needed so that gaming has priority over homelab workloads.

## Monitoring

Zabbix runs inside Docker on the Mac Mini and is used to monitor the infrastructure.

## Notifications

The homelab uses Telegram for operational event notifications.

Telegram credentials and tokens are not part of the public documentation.

## Updates

Docker service updates should be performed in a controlled manner, checking the service state before the update and validating operation afterwards.

## Recovery

Detailed backup and recovery procedures will be added as the storage and backup infrastructure is documented.
