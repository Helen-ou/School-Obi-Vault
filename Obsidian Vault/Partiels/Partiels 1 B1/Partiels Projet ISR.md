Création d'un réseau comprenant un poste client. 
Se souvenir de : 
- Firewall
- DNS
- DHCP
- Serveur Active Directory

**Modèle OSI et TCP/IP** => Open System Interconnection sert à standardiser et à organiser le processus de communication entre équipements dans un réseau. 7 Couches :
	1. Couche Physique
	2. Couche Liaison des Données
	3. Couche Réseau
	4. Couche Transport (TCP / UDP)
	5. Couche Session
	6. Couche Présentation (Cryptage)
	7. Couche Application
**Pour Le Réseau, Tout Se Passe Automatiquement**

**Gérer masque de sous réseau :**

Masque de sous-réseau :
192.168.1.1
255.255.255.128
25 = nombre de 1 binaire dans le masque (11111111 11111111 11111111 10000000)
Donc le masque de sous-réseau est 25 d'où :
192.168.1.1/25
Adresse réseau : 198.168.1.0/25
IP de 1-126

**DNS :** Le serveur Domain Naim System est un serveur informatique (annuaire) qui répond aux requêtes DNS. Essentiel à Internet (ne pas avoir à écrire les adresse IP à la mano)

**DHCP :** Dynamic Host Configuration Protocol est un service réseau qui permet d'attribuer de manière automatique et dynamique des adresses IP à des périphériques client sur un réseau local.
Permet d'avoir accès à internet. Automatise la configuration réseau des périphérique et simplifier l'administration du réseau. 

**Pare-feu :** Un pare feu réseau / firewall est un système de sécurité informatique (OPNsense va être utilisé) qui permet de réguler en contrôlant les communications entrantes et sortantes.
Filtre le trafic réseau en utilisant des règles prédéfinies pour autoriser ou bloquer les communications 

**Active Directory :** Active Directory est un serveur informatique qui utilise le service d'annuaire Microsoft Active Directory pour gérer les identités et les autorisations 
C'est un arbre pour organiser et gérer. Frontière de sécurité. Se souvenir de l'expression *Politiques de Groupe*.
Référer à [[Création AD]] pour plus d'infos.

