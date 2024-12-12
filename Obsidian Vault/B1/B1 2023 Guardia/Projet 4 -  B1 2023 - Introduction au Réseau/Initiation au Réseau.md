

Un réseau est un ensemble d'éléments interconnectés - ex :
- Réseaux Informatiques
- Réseaux Sociaux
- Réseaux de Transport

Équipements :
	Carte réseau / Carte Sans-fil
	Switch
	Routeur


Modèle OSI => Open System Interconnection sert à standardiser et à organiser le processus de communication entre équipements dans un réseau. 7 Couches :
	1. Couche Physique
	2. Couche Liaison des Données
	3. Couche Réseau
	4. Couche Transport (TCP / UDP)
	5. Couche Session
	6. Couche Présentation (Cryptage)
	7. Couche Application
Pour Le Réseau, Tout Se Passe Automatiquement

Modèle TCP/IP + utilisé que OSI. 4 Couches :
	1. Application
	2. Transport
	3. Internet
	4. Hôte Réseau

Configuration Réseau 
--

On y retrouve l'adresse MAC, l'adresse IP, la masse de sous-réseau, 
		MAC (Media Access Control) = Identifiant unique attribué à un dispositif réseau
		Adresse IPv4 (+ usuelle que IPv6)
		Masque de sous-réseau = Combien d'équipement sur le réseau + combien on peut mettre ex : 192.168.0.1/16


Masque de sous-réseau = Binaire valeur IP et ET logique avec masque
Adresse IP publique / privée : utilisation sur internet ou intranet


Routage Réseau
--

> Le routage réseau est le processus de transition de données entre différentes réseaux informatiques
> Utilisé pour acheminer des données d'un point d'origine à une destination à travers un réseau interconnecté
> Table de routage qui donne les routes à suivre (fillius pain). 
> On utilise un routeur

Masque de sous-réseau :
192.168.1.1
255.255.255.128
25 = nombre de 1 binaire dans le masque (11111111 11111111 11111111 10000000)
Donc le masque de sous-réseau est 25 d'où :
192.168.1.1/25
Adresse réseau : 198.168.1.0/25
IP de 1-126

Serveur DNS
--

Le serveur Domain Naim System est un serveur informatique (annuaire) qui répond aux requêtes DNS. Essentiel à Internet (ne pas avoir à écrire les adresse IP à la mano)

Serveur DHCP
--

Dynamic Host Configuration Protocol est un service réseau qui permet d'attribuer de manière automatique et dynamique des adresses IP à des périphériques client sur un réseau local.
Permet d'avoir accès à internet. Automatise la configuration réseau des périphérique et simplifier l'administration du réseau. 

Pare-Feu
--
Un pare feu réseau / firewall est un système de sécurité informatique (OPNsense va être utilisé) qui permet de réguler en contrôlant les communications entrantes et sortantes.
Filtre le trafic réseau en utilisant des règles prédéfinies pour autoriser ou bloquer les communications 

Serveur Active Directory
--

Active Directory est un serveur informatique qui utilise le service d'annuaire Microsoft Active Directory pour gérer les identités et les autorisations 
C'est un arbre pour organiser et gérer. Frontière de sécurité.

La Virtualisation
--

Utiliser Virtual Box / VMware / Hyper-V
Permet de faciliter par l'utilisation d'un hyperviseur. Ses rôles sont :
- L'isolation des ressources
- L'allocations des ressources
- Création et gestion des machines virtuelles 


