# Storage

## Overview

Homelab storage is distributed according to service requirements and data type.

## Media storage

The Media Stack uses separate paths for different types of content.

Current operational paths include:

- `D:\media\downloads`
- `D:\media\music`
- `D:\media\movies`
- `D:\media\tv`

The corresponding Docker paths are mounted inside the containers according to the Media Stack configuration.

## Temporary downloads

Incomplete downloads use dedicated directories within the Media Stack.

Separating incomplete downloads from final libraries provides a controlled import and processing workflow.

## Tdarr

Tdarr uses the media storage as the source and destination for processing.

The PCVR1 node also has a temporary directory mounted as `/temp` for processing.

## Docker storage

Docker configuration and persistent service data are kept separate from media data where required by the service configuration.

## Backups

The detailed backup policy will be documented in this section.

Backup documentation is not considered complete until destinations, schedule, retention and recovery procedures have been defined and validated.

## Future development

There is a future plan to migrate selected media services to a Synology NAS.

This migration is future work and is not part of the currently documented operational architecture.
