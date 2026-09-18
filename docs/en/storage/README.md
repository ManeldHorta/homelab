# Storage

## Overview

Homelab storage is distributed according to service requirements and data type.

PCVR1 currently has a single `D:` data disk with an approximate capacity of 8 TB. Available space is primarily used for active data storage.

## Media storage

The Media Stack uses separate paths for different types of content.

Current operational paths include:

- `D:\media\downloads`
- `D:\media\music`
- `D:\media\movies`
- `D:\media\tv`

The corresponding Docker paths are mounted inside the containers according to the Media Stack configuration.

## Temporary downloads

Incomplete downloads use dedicated directories within the Media Stack structure.

Separating incomplete downloads from final libraries provides a controlled import and processing workflow.

## Tdarr

Tdarr uses the media storage as the source and destination for processing.

The PCVR1 node also has a temporary directory mounted as `/temp` for processing.

Tdarr persistent configuration is kept separate from media data:

- `D:\docker\tdarr\server` → `/app/server`
- `D:\docker\tdarr\configs` → `/app/configs`
- `D:\docker\tdarr\logs` → `/app/logs`
- `D:\cache` → `/temp`
- `D:\Media` → `/media`

## Docker storage

Docker persistent data and service configuration are kept separate from media data where required by the service configuration.

## Backups

A backup system is not currently implemented for the PCVR1 data disk.

PCVR1 currently uses a single data disk for media and homelab data. Available storage is intentionally used for active data rather than maintaining a local backup copy.

A dedicated backup strategy will be designed as part of the future migration to a Synology NAS.

The future backup design will define:

- Backup destinations
- Backup schedule
- Retention policy
- Recovery procedures
- Protection of critical configuration data

## Future development

There is a future plan to migrate selected media services to a Synology NAS.

This migration is future work and is not part of the currently documented operational architecture.
