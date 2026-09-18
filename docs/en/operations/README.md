
Operations
Overview

This section documents the operational procedures used to maintain the homelab.

Docker

Docker services are managed through Docker Compose and Portainer.

Operational procedures should cover:

Deployment
Updates
Restart
Logs
Troubleshooting
Recovery
Media Operations

The media stack automates:

Downloading
Importing
Organisation
Video transcoding
Library management
Media playback
Tdarr Operations

Tdarr processes movies and TV series.

Music is excluded from the video transcoding workflow.

The current video target is H.265 / HEVC.

NVIDIA NVENC is used for GPU video encoding.

Notifications

Telegram notifications are used for media-stack events.

The intended notifications include:

Completed qBittorrent downloads
Completed Tdarr conversions

Credentials for Telegram are stored outside the public repository.

Monitoring

Zabbix is used to monitor infrastructure and services.

Recovery

Recovery procedures will document how to restore:

Docker services
Configuration
Media libraries
Monitoring
AI services

Detailed recovery procedures will be added after the infrastructure inventory is completed.
