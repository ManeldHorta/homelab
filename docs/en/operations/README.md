# Operations

## Overview

This section documents the operational procedures of the homelab.

## Docker

The main services run with Docker.

PCVR1 is the main Docker host and runs:

- UniFi OS
- Media Stack
- Tdarr
- Local AI environment

The Mac Mini also runs Docker and hosts Zabbix.

## Media Stack

The Media Stack includes download and media management services.

The PCVR1 Media Stack download services are not necessarily kept running during gaming sessions. They can be started on demand or operate during the overnight window from 00:00 to 07:30.

## Operational Automation

The PCVR1 Media Stack has automated tasks managed through Windows Task Scheduler.

### Media Stack

The Media Stack is automatically started and stopped according to the following schedule:

- Start: every day at 00:00.
- Stop: every day at 07:30.

The scheduled tasks use the following scripts:

- `C:\scripts\start-mediastack.ps1`
- `C:\scripts\stop-mediastack.ps1`

The start script:

1. Starts Docker Desktop.
2. Waits until the Docker daemon responds.
3. Starts the Media Stack containers.
4. Starts Tdarr and its node.

The stop script stops the Media Stack and Tdarr containers.

### Tdarr Watchdog

Tdarr has a dedicated watchdog for the PCVR1 GPU node.

The `TdarrNode-Watchdog` scheduled task runs:

- every 5 minutes;
- during the 00:00 to 07:30 window;
- using `C:\scripts\watch-tdarr-node.ps1`.

The watchdog checks recent `tdarr-node` logs and specifically detects the following errors:

- `MODULE_NOT_FOUND`
- `Cannot find module`

When one of these errors is detected, it:

1. Sends a Telegram notification.
2. Automatically restarts the `tdarr-node` container.
3. Records the incident in `C:\scripts\tdarr-watch.log`.

The restart is performed directly through Docker and affects only the `tdarr-node` container.

The `tdarr-node` container also uses the Docker policy:

`restart: always`

This policy provides an additional container recovery mechanism.

Telegram credentials and tokens are not included in the public documentation.

## Tdarr

Tdarr is used for video processing.

The current objective is to convert video to H.265 / HEVC to reduce the need for transcoding during playback.

Tdarr uses the PCVR1 GPU node with an NVIDIA RTX 4080, and the current stable configuration uses four GPU workers.

## Local AI

The local AI environment runs on PCVR1.

AI services are only started when needed, so gaming has priority over homelab workloads.

## Monitoring

Zabbix runs in Docker on the Mac Mini and is used to monitor the infrastructure.

## Notifications

The homelab uses Telegram to receive operational event notifications.

Telegram credentials and tokens are not included in the public documentation.

## Updates

Docker service updates should be performed in a controlled manner, checking the service state beforehand and validating its operation afterwards.

## Recovery

Detailed backup and recovery procedures will be added as the storage and backup infrastructure is documented.