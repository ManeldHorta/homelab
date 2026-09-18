# Seguretat

## Visió general

La seguretat del homelab es basa en la separació de funcions, el control dels serveis i una gestió ordenada de la infraestructura.

L'arquitectura actual és una infraestructura domèstica en evolució. La segmentació avançada de la xarxa i el control centralitzat del trànsit formen part de l'arquitectura futura.

## Xarxa i segmentació

La infraestructura de xarxa actual utilitza un gateway domèstic i equipament UniFi per a la connectivitat de la xarxa local.

Actualment no hi ha VLANs 802.1Q implementades. Les xarxes Wi-Fi `PCVR`, `Dispositius` i `IoT` corresponen a SSID diferenciats i no constitueixen VLANs reals.

La futura arquitectura incorporarà un router/firewall propi amb VLANs i regles de control d'accés per separar els diferents tipus de dispositius i serveis.

## Serveis i Docker

Els serveis del homelab s'executen principalment amb Docker i es distribueixen en diferents projectes Compose segons la seva funció.

Portainer s'utilitza per a l'administració dels contenidors.

Les configuracions i dades persistents dels serveis es mantenen separades de les dades multimèdia quan la configuració del servei ho requereix.

## Secrets i credencials

El repositori públic no ha de contenir:

- contrasenyes;
- tokens;
- claus d'autenticació;
- secrets d'API;
- credencials de serveis;
- identificadors sensibles relacionats amb l'accés remot.

Les credencials i tokens de serveis externs no formen part de la documentació pública.

La informació operativa sensible que sigui necessària per a la recuperació es mantindrà al repositori privat o en un sistema d'emmagatzematge segur.

## Actualitzacions

Les actualitzacions dels serveis i components de la infraestructura s'han de realitzar de manera controlada.

Abans d'actualitzar:

1. Comprovar l'estat del servei.
2. Identificar els canvis previstos.
3. Disposar d'una via de recuperació quan sigui necessari.

Després d'actualitzar:

1. Comprovar que el servei està funcionant.
2. Validar les funcionalitats principals.
3. Revisar els logs si s'ha produït algun comportament inesperat.

## Recuperació

La documentació pública descriu l'arquitectura i els principis operatius, però no conté els detalls necessaris per reproduir o recuperar completament la infraestructura.

Els procediments detallats de recuperació, les configuracions internes i altres dades operatives sensibles es mantindran a la documentació privada.

Els secrets s'han de mantenir fora de Git sempre que sigui possible, inclòs el repositori privat.

## Arquitectura futura

La futura arquitectura de seguretat està prevista al voltant de:

- router/firewall propi;
- VLANs reals per separar els diferents tipus de dispositius i serveis;
- regles de firewall i control de trànsit entre VLANs;
- accés remot mitjançant una VPN gestionada pel router;
- migració progressiva de l'arquitectura d'accés remot actual.

Aquest disseny es definirà quan es realitzi la migració al router propi.

## Informació sensible

La documentació pública evita publicar informació que no sigui necessària per entendre l'arquitectura, com ara:

- adreces internes completes;
- configuracions de firewall;
- configuracions detallades d'accés remot;
- claus i tokens;
- credencials;
- informació detallada dels dispositius autoritzats;
- dades que facilitin la reproducció de la configuració interna.

La documentació privada funcionarà com a referència de recuperació i podrà contenir els detalls operatius necessaris, mantenint els secrets fora de Git sempre que sigui possible.
