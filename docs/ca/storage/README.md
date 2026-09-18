# Emmagatzematge

## Visió general

L'emmagatzematge del homelab es distribueix segons el tipus de servei i les necessitats de les dades.

## Emmagatzematge multimèdia

El Media Stack utilitza una estructura separada per als diferents tipus de contingut.

Les rutes operatives actuals inclouen:

- `D:\media\downloads`
- `D:\media\music`
- `D:\media\movies`
- `D:\media\tv`

Els directoris de Docker corresponents es munten dins dels contenidors segons la configuració del Media Stack.

## Descàrregues temporals

Les descàrregues incompletes utilitzen directoris específics del Media Stack.

La separació entre descàrregues incompletes i biblioteques finals permet mantenir un flux controlat d'importació i processament.

## Tdarr

Tdarr utilitza l'emmagatzematge multimèdia com a origen i destinació del processament.

El node de PCVR1 disposa també d'un directori temporal muntat com `/temp` per al processament.

## Emmagatzematge de Docker

La configuració i les dades persistents dels serveis Docker es mantenen separades de les dades multimèdia quan la configuració del servei ho requereix.

## Còpies de seguretat

La política detallada de còpies de seguretat encara es documentarà en aquest apartat.

No es considera completada la documentació de backup fins que les destinacions, periodicitat, retenció i procediments de recuperació estiguin definits i validats.

## Evolució futura

Existeix una planificació per migrar determinats serveis multimèdia cap a un NAS Synology.

Aquesta migració és futura i no forma part de l'arquitectura operativa actual documentada.
