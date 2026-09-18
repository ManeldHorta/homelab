# PCVR1



## Descripció



PCVR1 és un equip de gaming que també s'utilitza com a servidor per allotjar diferents serveis del homelab.



L'objectiu principal és aprofitar els recursos disponibles de l'equip sense comprometre el seu ús principal com a plataforma de gaming.



Per aquest motiu, els serveis que poden generar una càrrega elevada no funcionen de manera permanent.



## Funcions principals



Les principals funcions actuals de PCVR1 són:



- Equip de gaming

- Host Docker

- UniFi OS

- Media Stack

- Processament de vídeo amb Tdarr

- Intel·ligència artificial local



## Principi d'ús compartit de recursos



PCVR1 comparteix els seus recursos entre el gaming i els serveis del homelab.



La prioritat de l'equip és mantenir el rendiment del gaming.



Els serveis que poden generar una càrrega elevada de CPU, GPU, memòria, disc o xarxa s'executen seguint una política d'activació controlada.



Aquesta política evita que els serveis del homelab interfereixin amb l'ús interactiu de l'equip.



## Política d'activació dels serveis



### Media Stack



Els serveis del Media Stack relacionats amb les descàrregues no funcionen permanentment.



Els serveis de descàrrega s'activen en un dels casos següents:



- A demanda.

- Automàticament durant la franja nocturna, de 00:00 a 07:30.



Aquesta política permet aprofitar l'equip durant les hores en què normalment no s'utilitza per jugar i evitar càrrega de xarxa, disc i processador durant les sessions de gaming.



### Intel·ligència artificial local



Els serveis d'intel·ligència artificial local només s'activen a demanda.



No es mantenen executant de manera permanent.



Aquesta política és especialment important perquè alguns workloads d'IA poden utilitzar una quantitat significativa de recursos, especialment GPU.



## Tdarr



Tdarr utilitza la GPU de PCVR1 per al processament i conversió de vídeo.



El node GPU de Tdarr s'identifica com:



PCVR1



El node utilitza una GPU NVIDIA RTX 4080.



La configuració actual estable utilitza quatre GPU workers.



La seva execució forma part de la política general de gestió de recursos de PCVR1, ja que el processament de vídeo pot generar una càrrega elevada sobre la GPU.



## UniFi OS



PCVR1 allotja actualment UniFi OS.



UniFi OS estava anteriorment allotjat al Mac Mini, però es va traslladar a PCVR1 perquè l'espai d'emmagatzematge del Mac Mini és limitat.



## Media Stack



PCVR1 allotja el Media Stack principal del homelab.



Els components principals són:



- qBittorrent

- Radarr

- Sonarr

- Lidarr

- Prowlarr

- Jackett



Els serveis relacionats amb les biblioteques multimèdia inclouen:



- Jellyfin

- Navidrome

- Komga



Els serveis de descàrrega del Media Stack estan subjectes a la política d'activació definida anteriorment.



## Intel·ligència artificial local



PCVR1 allotja l'entorn d'intel·ligència artificial local dins de Docker.



Els components documentats inclouen:



- Ollama

- Open WebUI

- ComfyUI

- Coqui TTS

- Piper

- Presenton

- ACE-Step



Els serveis d'IA només s'activen a demanda.



L'entorn està dissenyat per mantenir el processament d'IA dins de la infraestructura local.



## Estat actual



PCVR1 és un equip de gaming amb funcions addicionals de servidor.



La seva arquitectura està dissenyada al voltant del principi següent:



Gaming > serveis del homelab



Els serveis permanents o de baixa càrrega poden coexistir amb l'ús habitual de l'equip, mentre que els serveis amb potencial d'impacte sobre el rendiment s'activen de manera controlada.



Aquesta arquitectura permet disposar de capacitats de servidor, processament multimèdia i intel·ligència artificial sense dedicar un equip exclusivament a aquestes funcions.

