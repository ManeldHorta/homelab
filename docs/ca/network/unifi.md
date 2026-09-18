# UniFi

## Funció

La infraestructura de xarxa local està gestionada mitjançant equipament UniFi.

## Components actuals

- USW Flex 2.5G 8 PoE — switch principal.
- USW Flex 2.5G 5 — switch secundari.
- U7 Pro — punt d'accés Wi-Fi.
- U7 Lite — punt d'accés Wi-Fi.

## Topologia física

Livebox FIBRA
      │
      ▼
USW Flex 2.5G 8 PoE
 ├── U7 Pro
 ├── U7 Lite
 ├── USW Flex 2.5G 5
 ├── Mac Mini
 └── PCVR1

USW Flex 2.5G 5
 ├── PCVR2
 └── TV

## Enllaços principals

- USW Flex 2.5G 8 PoE → USW Flex 2.5G 5: 2,5 GbE.
- PCVR1 → switch principal: 5 GbE.
- Mac Mini → switch principal: 2,5 GbE.
- PCVR2 → switch secundari: 2,5 GbE.
- TV → switch secundari: Fast Ethernet.
- Els dos punts d'accés estan connectats al switch principal i reben alimentació PoE.

## STP

UniFi mostra STP actiu en l'enllaç entre els dos switches.

## Recuperació

La informació detallada necessària per reconstruir la infraestructura —IP, MAC, firmware i altres paràmetres operatius— es reservarà per al repositori privat de recuperació.
