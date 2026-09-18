
Seguretat
Principis

El homelab segueix un model de seguretat local-first.

Els principals objectius sÃ³n:

Minimitzar l'exposiciÃ³ innecessÃ ria a Internet
Mantenir les dades sensibles localment
Separar la documentaciÃ³ pÃºblica de la configuraciÃ³ privada
Utilitzar segmentaciÃ³ de xarxa quan sigui apropiat
Monitoritzar l'estat de la infraestructura
Mantenir configuracions recuperables
Credencials

Les credencials no s'han de publicar mai al repositori pÃºblic.

Per exemple:

Contrasenyes
Claus API
Tokens del bot de Telegram
Claus SSH
Certificats privats
Credencials de bases de dades
Repositoris pÃºblic i privat

El repositori pÃºblic contÃ© documentaciÃ³ i exemples de configuraciÃ³ sanejats.

La informaciÃ³ sensible es mantÃ© al repositori privat:

homelab-private
GestiÃ³ de secrets

Els exemples pÃºblics han d'utilitzar placeholders en lloc de credencials reals.

Exemple:

TELEGRAM_BOT_TOKEN=
TELEGRAM_CHAT_ID=
RADARR_API_KEY=
SONARR_API_KEY=
LIDARR_API_KEY=
Seguretat de xarxa

La segmentaciÃ³ de xarxa, les regles de firewall i la limitaciÃ³ de l'exposiciÃ³ dels serveis formen part de l'arquitectura de seguretat.

La configuraciÃ³ detallada de seguretat de xarxa es documentarÃ  desprÃ©s de completar l'inventari de xarxa.
