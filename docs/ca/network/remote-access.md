# Accés remot

## Estat actual

Actualment s'utilitza Tailscale per proporcionar accés remot als serveis interns del homelab.

Tailscale permet accedir als serveis sense exposar directament els seus ports a Internet.

## Arquitectura actual

L'accés remot es realitza mitjançant la xarxa Tailscale dels dispositius autoritzats.

La configuració detallada, els nodes i les polítiques d'accés es mantenen fora de la documentació pública.

## Arquitectura futura

Tailscale es considera una solució temporal.

Quan s'instal·li el router/firewall propi, està prevista la seva substitució per un sistema d'accés remot gestionat pel propi router, mitjançant VPN.

Aquesta futura arquitectura formarà part del disseny de firewall, VLANs i control d'accés de la xarxa.

## Seguretat

No es publiquen:

- claus ni tokens de Tailscale;
- identificadors dels nodes;
- configuracions ACL;
- adreces internes;
- configuracions que permetin reproduir l'accés remot.
