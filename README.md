# Homelab

Self-hosted infrastructure, architecture, services and operational documentation.

## Documentation

All documentation is available in English and Catalan.

### English

- [Architecture](docs/en/architecture/)
- [Network](docs/en/network/)
- [Servers](docs/en/servers/)
- [Storage](docs/en/storage/)
- [Services](docs/en/services/)
- [Security](docs/en/security/)
- [Operations](docs/en/operations/)

### Català

- [Arquitectura](docs/ca/architecture/)
- [Xarxa](docs/ca/network/)
- [Servidors](docs/ca/servers/)
- [Emmagatzematge](docs/ca/storage/)
- [Serveis](docs/ca/services/)
- [Seguretat](docs/ca/security/)
- [Operacions](docs/ca/operations/)

## Infrastructure

This homelab is built around a local-first and self-hosted approach.

Main infrastructure areas:

- Local network
- Servers and storage
- Docker infrastructure
- Media Stack
- Local AI
- Monitoring
- Backup and recovery

## Services

### Media Stack

- qBittorrent
- Radarr
- Sonarr
- Lidarr
- Tdarr
- Jellyfin

### Local AI

Local AI infrastructure running inside the home network, including natural-language interaction and local generation of images, video, voice, music and Catalan speech.

### Monitoring

- Zabbix

## Design Principles

- Self-hosted whenever practical
- Local-first data processing
- No unnecessary exposure to the Internet
- Reproducible configuration
- Separation between public documentation and private configuration
- Monitoring and observability
- Automation over manual operations

## Repository Structure

`	ext
docs/               Documentation in English and Catalan
infrastructure/     Infrastructure configuration
services/            Service-specific configuration
scripts/             Utility scripts
diagrams/            Architecture diagrams
examples/            Sanitised configuration examples
`"
"


This public repository intentionally contains no passwords, API keys, tokens or other credentials.

Sensitive configuration and private operational information are maintained separately in the private repository.

---

# Homelab

Infraestructura self-hosted, arquitectura, serveis i documentació operativa.

## Documentació

Tota la documentació està disponible en anglès i català.

### English

- [Architecture](docs/en/architecture/)
- [Network](docs/en/network/)
- [Servers](docs/en/servers/)
- [Storage](docs/en/storage/)
- [Services](docs/en/services/)
- [Security](docs/en/security/)
- [Operations](docs/en/operations/)

### Català

- [Arquitectura](docs/ca/architecture/)
- [Xarxa](docs/ca/network/)
- [Servidors](docs/ca/servers/)
- [Emmagatzematge](docs/ca/storage/)
- [Serveis](docs/ca/services/)
- [Seguretat](docs/ca/security/)
- [Operacions](docs/ca/operations/)

## Infraestructura

Aquest homelab està basat en un model local-first i self-hosted.

Àrees principals:

- Xarxa local
- Servidors i emmagatzematge
- Infraestructura Docker
- Media Stack
- IA local
- Monitorització
- Còpies de seguretat i recuperació

## Serveis

### Media Stack

- qBittorrent
- Radarr
- Sonarr
- Lidarr
- Tdarr
- Jellyfin

### IA local

Infraestructura d'IA local executada dins de la xarxa domèstica, incloent interacció en llenguatge natural i generació local d'imatges, vídeo, veu, música i veu en català.

### Monitorització

- Zabbix

## Principis de disseny

- Self-hosted sempre que sigui pràctic
- Processament local de les dades
- Minimitzar l'exposició innecessària a Internet
- Configuració reproduïble
- Separació entre documentació pública i configuració privada
- Monitorització i observabilitat
- Automatització de tasques repetitives

## Seguretat

Aquest repositori públic no conté intencionadament contrasenyes, claus API, tokens ni altres credencials.

La configuració sensible i la informació operativa privada es mantenen separades al repositori privat.
