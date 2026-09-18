# Seguretat

## Principis

El homelab segueix un enfocament local-first.

Els objectius principals són:

- Minimitzar l'exposició innecessària a Internet.
- Mantenir les dades sensibles fora del repositori públic.
- Separar configuració pública i informació privada.
- Aplicar segmentació de xarxa quan sigui apropiat.
- Monitoritzar l'estat de la infraestructura.

## Credencials

Les credencials no s'han de publicar mai al repositori públic.

Això inclou:

- Contrasenyes
- Tokens
- Claus API
- Claus SSH
- Certificats privats
- Credencials de bases de dades

## Telegram

Les notificacions de Telegram formen part de l'operació del homelab.

El token del bot i el chat ID són informació privada i no s'han d'incloure en cap document públic.

## Git

El repositori públic conté documentació de la infraestructura sense secrets operatius.

Els fitxers de configuració que continguin credencials, secrets o dades privades s'han de mantenir fora del repositori públic.

## Xarxa

La segmentació de xarxa, les VLAN i les regles de firewall s'utilitzen per limitar la comunicació entre diferents tipus de dispositius i serveis.

Els detalls que puguin exposar informació sensible de la xarxa s'han de revisar abans de publicar-se.

## Serveis locals

Els serveis d'IA local es mantenen dins de la infraestructura local.

L'objectiu és evitar enviar a Internet les dades utilitzades per aquests serveis.

## Principi de mínima exposició

Només s'han d'exposar els serveis que siguin realment necessaris.

Els ports, credencials i configuracions detallades es documentaran només quan sigui necessari i sense incloure secrets.
