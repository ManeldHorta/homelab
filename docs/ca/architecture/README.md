
Arquitectura del Homelab
VisiÃ³ general

Aquest homelab Ã©s una infraestructura self-hosted centrada en serveis locals, automatitzaciÃ³, gestiÃ³ multimÃ¨dia i intelÂ·ligÃ¨ncia artificial local.

La infraestructura estÃ  organitzada principalment al voltant de contenidors Docker i recursos locals de cÃ²mput i emmagatzematge.

Ã€rees principals
Infraestructura i gestiÃ³ de contenidors
GestiÃ³ i processament multimÃ¨dia
Consum de continguts i serveis multimÃ¨dia
IntelÂ·ligÃ¨ncia artificial local
MonitoritzaciÃ³ i operacions
Emmagatzematge i cÃ²pies de seguretat
Arquitectura Docker
Infraestructura
Portainer â€” gestiÃ³ i administraciÃ³ de Docker
Media Stack
qBittorrent â€” client de descÃ rregues
Radarr â€” gestiÃ³ de pelÂ·lÃ­cules
Sonarr â€” gestiÃ³ de sÃ¨ries
Lidarr â€” gestiÃ³ de mÃºsica
Prowlarr â€” gestiÃ³ d'indexadors
Jackett â€” integraciÃ³ d'indexadors
Tdarr â€” processament multimÃ¨dia i transcodificaciÃ³ de vÃ­deo
Serveis multimÃ¨dia
Jellyfin â€” reproducciÃ³ de vÃ­deo i contingut multimÃ¨dia
Navidrome â€” servidor de mÃºsica
Komga â€” cÃ²mics i lectura digital
Dashy â€” panell de serveis self-hosted
IA local
Ollama â€” execuciÃ³ local de models de llenguatge
Open WebUI â€” interfÃ­cie web per a IA local
ComfyUI â€” generaciÃ³ d'imatges i fluxos de treball d'IA
Coqui TTS â€” text a veu
Piper â€” text a veu
Presenton â€” generaciÃ³ de presentacions amb IA
ACE-Step â€” generaciÃ³ local de mÃºsica
Flux de dades multimÃ¨dia
                    DescÃ rrega
                        |
                        v
                   qBittorrent
                        |
              +---------+---------+
              |                   |
              v                   v
            Radarr              Sonarr
              |                   |
              +---------+---------+
                        |
                        v
               Biblioteques multimÃ¨dia
                        |
                        v
                      Tdarr
                        |
                        v
                   H.265 / HEVC
                        |
                        v
                    Jellyfin

Lidarr gestiona el flux de mÃºsica de manera independent.

La mÃºsica s'emmagatzema separadament i no passa pel pipeline de transcodificaciÃ³ de vÃ­deo de Tdarr.

Navidrome proporciona accÃ©s a la biblioteca musical.

Komga proporciona accÃ©s a la biblioteca de cÃ²mics.

Dashy proporciona un panell central per accedir als serveis self-hosted.

Processament de vÃ­deo

Tdarr s'utilitza per normalitzar el contingut de vÃ­deo a H.265 / HEVC.

Els fitxers que ja estan codificats en HEVC no es tornen a transcodificar innecessÃ riament.

El vÃ­deo que no Ã©s HEVC es pot transcodificar mitjanÃ§ant NVIDIA NVENC.

El flux de Tdarr tambÃ© gestiona les pistes d'Ã udio i els subtÃ­tols segons les regles configurades d'idioma i qualitat.

El flux actual utilitza un plugin clÃ ssic local de Tdarr i un Flow format per:

Input File
    |
    v
Run Classic Transcode Plugin
    |
    v
Replace Original File

El pas de substituciÃ³ Ã©s necessari perquÃ¨ el fitxer processat es crea inicialment a la memÃ²ria cau de transcodificaciÃ³ de Tdarr.

Arquitectura de la IA local

L'entorn d'IA local estÃ  dissenyat per mantenir el processament d'IA dins de la infraestructura domÃ¨stica sempre que sigui possible.

Ollama proporciona l'execuciÃ³ local de models de llenguatge.

Open WebUI proporciona una interfÃ­cie web per interactuar amb els models d'IA locals.

Altres serveis proporcionen generaciÃ³ local d'imatges, sÃ­ntesi de veu, generaciÃ³ de presentacions i generaciÃ³ de mÃºsica.

                       IA local
                          |
          +---------------+---------------+
          |               |               |
          v               v               v
       Ollama          ComfyUI       Open WebUI
          |               |               |
          +---------------+---------------+
                          |
                 Altres serveis d'IA
                 TTS / presentacions / mÃºsica
GestiÃ³ dels contenidors

Portainer proporciona l'administraciÃ³ central de l'entorn Docker.

MonitoritzaciÃ³ i operacions

Zabbix s'utilitza com a plataforma de monitoritzaciÃ³ de la infraestructura del homelab.

L'automatitzaciÃ³ s'utilitza per a l'adquisiciÃ³, organitzaciÃ³ i transcodificaciÃ³ multimÃ¨dia i per a les notificacions.

Les notificacions de Telegram estan integrades en el flux multimÃ¨dia per informar dels esdeveniments rellevants de descÃ rrega i transcodificaciÃ³.

Seguretat i privacitat

La infraestructura segueix un enfocament local-first.

Els serveis que no necessiten accÃ©s extern estan pensats per romandre dins de la xarxa local.

Aquest repositori pÃºblic no ha de contenir:

Contrasenyes
Claus API
Tokens d'accÃ©s
Tokens de bots
Certificats privats
Claus privades
Altres credencials

La configuraciÃ³ sensible es mantÃ© separadament al repositori privat del homelab.

Estat de la documentaciÃ³

Encara cal completar un inventari detallat de:

Hardware fÃ­sic dels servidors
MÃ quines virtuals
Topologia de xarxa
ConfiguraciÃ³ del router i firewall
Infraestructura UniFi
ConfiguraciÃ³ de VLANs
Arquitectura d'emmagatzematge
EstratÃ¨gia de cÃ²pies de seguretat
AccÃ©s remot
Mapejos detallats dels volums Docker
DependÃ¨ncies entre serveis
Arquitectura de monitoritzaciÃ³
