# Infrastructure

This directory contains the infrastructure definitions and deployment material used to build and operate the homelab.

The current environment uses Docker on PCVR1 and the Mac Mini.

Known Docker Compose projects include:

- Dashy;
- Local AI;
- Jellyfin;
- Komga;
- Media Stack;
- Navidrome;
- Portainer;
- Tdarr.

The actual Compose files and deployment-specific configuration should be added here only when they are ready to be version-controlled.

Sensitive configuration and secrets must not be committed.

## Current architecture

PCVR1 is the main Docker host and runs most homelab services.

The Mac Mini is a secondary Docker host and currently runs Zabbix.

Infrastructure definitions should represent the actual deployed state and distinguish future or experimental configurations from production use.
