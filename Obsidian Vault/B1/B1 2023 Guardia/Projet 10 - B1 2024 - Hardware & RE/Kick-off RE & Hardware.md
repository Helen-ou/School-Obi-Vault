<h3>Rappels</h3>

SPI :
> MISO
> MOSI
> CS (Safe Select)
> Clock

SOP8 : Composant de surface (sur un PCB?)
UART : Universal Asynchronous Receive Transmitter

Pull-up / pull-down permet de mettre une valeur par défaut (par défaut état haut / bas)

<h3>2nd Projet</h3>

<h4>Rétro-ingénierie &  protocoles numériques</h4>
> Programmation embarquée = lire une datasheet et écrire un driver

Pourquoi ? :
> Pentest hardware/IoT
> Right to repair
> Circuit bending

<h6>La fabrication de PCBs</h6>
- Schéma
- Design
- Fabrication
- Assemblage
- (Programmation)
- Des Tests à chaque étape

Nyquist (Mathématicien) : $$F{x} = \frac{f{x}}{2}$$

Composants passifs en surface :
> Résistance = carré noir
> Condensateur = carré orange 
> Bobines (coils) = bobines (ne pas s'y intéresser, en outre)

Intéressant = circuit intégré est une puce qui a plein de fonctionnalités

<h4>Consignes de Sécurité</h4>

Faite attention au niveau de mesure de la sonde de l'oscilloscope ! 
<mark >Stabiliser la zone de travail. Si pas confortable, quelque chose ne va pas !</mark>
Les GND sont reliés ensemble.
On ne modifie pas un circuit allumé!
Batteries :
- Court circuit
- Over/Undervoltage


- **Plage d’entrée** :
    - **Différentiel** : ±2,5 V par rapport à la masse (5 V crête à crête)
    - **Simple-ended** : ±25 V par rapport à la masse (50 V crête à crête)
- **Résolution** : 14 bits (16 bits avec moyennage)
- **Précision** :
    - Pour les échelles inférieures ou égales à 0,

Fréquence de 100MhZ
Sondes :

- **Plage de tension d’entrée** :
    - **Différentiel** : ±25 V par rapport à la masse (50 V crête à crête)
    - **Simple-ended** : ±50 V par rapport à la masse (100 V crête à crête)
- **Bande passante** : 6 MHz (pour une sonde 1x)
- **Atténuation** : Les sondes 1x ont une atténuation de 1, tandis que les sondes 10x ont une atténuation de 10.


Analyseur logique = Voir si l'était est High ou Low. 
C'est donc beaucoup moins cher

<h5>Protocoles Numériques</h5>

UART : Permet de communiquer sans clock commune entre les appareils. Standardisé en 1962.

8N1 est la configuration standard d'un signal UART avec 8 bits de donnée, pas de bit de parité et 1 bit de stop

<h5>Logic Levels</h5>
Ce sont des protocoles de la couche 1 OSI (Physique)
TTL, CMOS : Transistor Translator Logic, Complementary Metal Oxide Serial Conductor
RS232 : Normalement, 1 est entre -3 et -15V et 0 entre +3 et +15V. Un signal entre est indéfini.
RS485 : Protocole industriel. Enlever le bruit en passant par une paire différentiel (2 courants qu'on soustrait à l'autre) 

<h5>La mémoire flash</h5>

Retenir 25 et 24



$\frac{owo}{w}$