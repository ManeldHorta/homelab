# Storage

## Visió general

L'emmagatzematge del homelab es distribueix segons les necessitats dels serveis i el tipus de dades.

PCVR1 disposa actualment d'un únic disc de dades `D:` amb una capacitat aproximada de 8 TB. L'espai disponible es destina principalment a l'emmagatzematge de dades actives.

## Emmagatzematge multimèdia

El Media Stack utilitza rutes separades segons el tipus de contingut.

Les rutes operatives actuals són:

- `D:\media\downloads`
- `D:\media\music`
- `D:\media\movies`
- `D:\media\tv`

Les rutes corresponents dins de Docker es munten segons la configuració del Media Stack.

## Descàrregues temporals

Les descàrregues incompletes utilitzen directoris específics dins de l'estructura del Media Stack.

La separació entre les descàrregues incompletes i les biblioteques finals permet mantenir un flux controlat d'importació i processament.

## Tdarr

Tdarr utilitza l'emmagatzematge multimèdia com a origen i destinació del processament.

El node de PCVR1 disposa també d'un directori temporal muntat com `/temp` per al processament.

La configuració persistent de Tdarr es manté separada de les dades multimèdia:

- `D:\docker\tdarr\server` → `/app/server`
- `D:\docker\tdarr\configs` → `/app/configs`
- `D:\docker\tdarr\logs` → `/app/logs`
- `D:\cache` → `/temp`
- `D:\Media` → `/media`

## Emmagatzematge Docker

Les dades persistents i la configuració dels serveis Docker es mantenen separades de les dades multimèdia quan la configuració del servei ho requereix.

## Còpies de seguretat

Actualment no hi ha implementat un sistema de còpies de seguretat per al disc de dades de PCVR1.

PCVR1 utilitza actualment un únic disc de dades per a les dades multimèdia i del homelab. L'espai disponible es destina intencionadament a l'emmagatzematge de dades actives en lloc de mantenir una còpia de seguretat local.

Es dissenyarà una estratègia específica de còpies de seguretat com a part de la futura migració a un NAS Synology.

El futur disseny de còpies de seguretat definirà:

- Destinacions de les còpies
- Planificació
- Política de retenció
- Procediments de recuperació
- Protecció de les configuracions crítiques

## Desenvolupament futur

Hi ha prevista una migració de determinats serveis multimèdia a un NAS Synology.

Aquesta migració és treball futur i no forma part de l'arquitectura operativa actualment documentada.
