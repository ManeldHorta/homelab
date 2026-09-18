
Emmagatzematge
VisiÃ³ general

L'emmagatzematge estÃ  dividit segons els requisits dels serveis i el tipus de dades.

Emmagatzematge multimÃ¨dia

La infraestructura multimÃ¨dia utilitza directoris separats per a:

PelÂ·lÃ­cules
SÃ¨ries
MÃºsica
DescÃ rregues
DescÃ rregues incompletes

L'entorn Docker mapeja aquests directoris del host als contenidors corresponents.

Processament multimÃ¨dia

Tdarr utilitza una memÃ²ria cau de transcodificaciÃ³ dedicada.

La configuraciÃ³ actual de Tdarr utilitza:

Media: /media
Transcode cache: /temp

AixÃ² permet que la transcodificaciÃ³ es faci a la memÃ²ria cau dedicada abans que el fitxer processat substitueixi el fitxer original.

Dades persistents

Els serveis Docker utilitzen directoris persistents de configuraciÃ³ perquÃ¨ recrear un contenidor no elimini l'estat de l'aplicaciÃ³.

CÃ²pies de seguretat

L'estratÃ¨gia completa de cÃ²pies de seguretat es documentarÃ  desprÃ©s de completar l'inventari d'emmagatzematge i backups.
