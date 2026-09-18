
Storage
Overview

Storage is divided according to service requirements and data type.

Media Storage

The media infrastructure uses separate directories for:

Movies
TV series
Music
Downloads
Incomplete downloads

The Docker environment maps these host directories into the relevant containers.

Media Processing

Tdarr uses a dedicated transcode cache.

The current Tdarr configuration uses:

Media: /media
Transcode cache: /temp

This allows transcoding work to take place in the dedicated cache before the processed file replaces the source file.

Persistent Application Data

Docker services use persistent configuration directories so that container recreation does not remove application state.

Backup

The complete backup strategy will be documented after the storage and backup inventory is completed.
