
Servers
Overview

This section documents the physical and virtual compute infrastructure used by the homelab.

Physical Infrastructure

The homelab includes local computers used for:

Docker
Virtual machines
Local AI
Media processing
Monitoring
Network management

The detailed hardware inventory will be added after collecting the current hardware specifications.

Virtual Machines

Virtual machines are used for selected infrastructure workloads.

The documentation will include:

Hypervisor
Operating system
CPU allocation
RAM allocation
Storage
Network configuration
Purpose
Docker Host

Docker is one of the main application platforms in the homelab.

Services are deployed as containers and persistent application data is stored outside the containers.

GPU

NVIDIA GPU acceleration is used by Tdarr for video transcoding.

The current Tdarr node uses NVIDIA NVENC for HEVC video encoding.

The detailed GPU and host hardware inventory will be documented separately.
