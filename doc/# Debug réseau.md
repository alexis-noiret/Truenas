# Debug réseau

## Contexte

La VM Debian cliente avait des difficultés d’accès réseau après installation.

## Symptômes

- `ping 8.8.8.8` en échec
- `Destination Host Unreachable`
- interface réseau `ens3` down
- route par défaut absente ou incorrecte

## Vérifications effectuées

Commandes utilisées :
- `ip a`
- `ip route`
- `ping 8.8.8.8`
- `ping 192.168.x.x`

## Causes identifiées

- mauvaise association de la carte réseau dans VMware
- confusion entre NAT et Bridged
- passerelle incorrecte
- réseau VM non cohérent avec le réseau réel

## Correctifs testés

- activation manuelle de l’interface
- ajout d’une IP manuelle
- ajout d’une route par défaut
- vérification du mode réseau VMware
- passage du réseau virtuel à une configuration cohérente

## Leçons retenues

Ce projet a permis de mieux comprendre :
- la différence entre NAT et Bridged
- le rôle de la gateway
- le comportement d’une interface réseau Linux
- l’importance de documenter les erreurs et les tests