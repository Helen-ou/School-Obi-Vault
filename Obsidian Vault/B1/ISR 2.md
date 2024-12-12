3 zones :
> DMZ
> Zone Administration (Serveurs admin..)
> Zone Cliente

Fonctionnalités :
> Reverse proxy et serveur web
> serveur AD
> service DHCP (uniquement sur cliente, admin = ip fixe)

service web doit être accessible par extérieur
Flux limités au minimum (internes et sortants)

![[Pasted image 20240318111548.png]]


Win server
Debian
OPNSense
AD / DNS / DHCP / Apache ou Nginx

debian reverse proxy et debian serveur web

Rendre dossier technique présentant l'installation et la configuration mise en place
Soutenance de 10-15m


Bonus automatisation

60 points sur sécu des flux

Le reverse proxy permet d'améliorer les performances du réseau en cachant (cache) les données web et ne pas faire 2 fois les mêmes requêtes

Zones réseau : DMZ LAN et WAN 

Segmenter réseau :
> + Sécure
> Meilleur gestion du trafic
> + Confidentiel

Les étapes :
> Analyse des besoins
> Identification des zones réseaux
> Définition des règles de sécurité
> Définition des politiques d'accès (IAM)
> Planification de l'architecture réseau
> Définition des adresses IP
> Mise en oeuvre et tests.

VLAN : VLAN basé sur les ports et VLAN balisés (Tagged VLAN)
