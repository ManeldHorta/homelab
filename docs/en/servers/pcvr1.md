# PCVR1



## Description



PCVR1 is a gaming computer that is also used as a server to host several homelab services.



The main objective is to make use of the system's available resources without compromising its primary purpose as a gaming platform.



For this reason, services that can generate significant resource usage are not necessarily kept running permanently.



## Main Roles



The main current roles of PCVR1 are:



- Gaming computer

- Docker host

- UniFi OS

- Media Stack

- Video processing with Tdarr

- Local Artificial Intelligence



## Shared Resource Policy



PCVR1 shares its resources between gaming and homelab services.



Gaming performance has priority.



Services that can generate significant CPU, GPU, memory, disk or network load are therefore operated according to a controlled activation policy.



This prevents homelab workloads from interfering with interactive use of the computer.



## Service Activation Policy



### Media Stack



The Media Stack services responsible for downloads are not permanently running.



Download services are activated in one of the following situations:



- On demand.

- Automatically during the night-time window from 00:00 to 07:30.



This policy allows the system to perform download-related workloads during periods when it is normally not being used for gaming, while reducing network, disk and processor activity during gaming sessions.



### Local Artificial Intelligence



Local AI services are only activated on demand.



They are not kept running permanently.



This is particularly important because some AI workloads can consume significant system resources, especially GPU resources.



## Tdarr



Tdarr uses the GPU in PCVR1 for video processing and conversion.



The Tdarr GPU node is identified as:



PCVR1



The node uses an NVIDIA RTX 4080 GPU.



The current stable configuration uses four GPU workers.



Its execution is part of the overall PCVR1 resource management policy because video processing can generate significant GPU load.



## UniFi OS



PCVR1 currently hosts UniFi OS.



UniFi OS was previously hosted on the Mac Mini but was moved to PCVR1 because the Mac Mini has limited local storage capacity.



## Media Stack



PCVR1 hosts the main Media Stack of the homelab.



The main components are:



- qBittorrent

- Radarr

- Sonarr

- Lidarr

- Prowlarr

- Jackett



Services related to the media libraries include:



- Jellyfin

- Navidrome

- Komga



The Media Stack download services are subject to the activation policy described above.



## Local Artificial Intelligence



PCVR1 hosts the local Artificial Intelligence environment inside Docker.



The documented components include:



- Ollama

- Open WebUI

- ComfyUI

- Coqui TTS

- Piper

- Presenton

- ACE-Step



AI services are only activated on demand.



The environment is designed to keep AI processing within the local infrastructure.



## Current Status



PCVR1 is a gaming computer with additional server capabilities.



Its architecture follows the following principle:



Gaming > homelab services



Permanent or low-load services can coexist with normal use of the computer, while services with a potential impact on performance are activated in a controlled manner.



This architecture provides server, media processing and local AI capabilities without requiring a dedicated system for these workloads.

