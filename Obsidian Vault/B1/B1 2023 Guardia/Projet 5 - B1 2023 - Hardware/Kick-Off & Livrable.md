###### 04/12
Objectif final :

Capteurs > Arduino > Actionneur
                    ^
                    |
                    ↓
                    Raspberry Pi
                    ^
                    |
                    ↓
                    Internet

Bases de l'électronique :
> Allumer une ampoule (2 câbles, une pile et une ampoule)
> Conducteur / Isolant
> Circuit ouvert / fermé (off/on)
> Courts-circuits
> Tension / Intensité / Résistance / Puissance + effet Joule (?)
> Batterie
> À quoi sert un multimètre ? Un oscilloscope ? Analyseur de signal, fer à souder ?

Tension est la différence entre 2 points d'un circuit. 
Intensité = vitesse (?) du circuit 
R = V/I
V = I\*R
I = V/R

breadboard : permet de composer des circuits électroniques
Diode : force le courant dans un sens
DEL / Diode électroluminescente : fais de la lumière dans un seul sens.
Résistance : Transforme le courant électronique en énergie thermique.

###### 05/12
Photorésistance : Résistance dont la valeur varie selon la lumière (capteur analogique)
Pas d'entrée Ohmmètre dans Arduino --> Pont diviseur de tension :
![[Pasted image 20231205133307.png]]
==Arduino : ==
C'est une : une marque, des cartes (programmable), un logiciel, un langage de programmation.
C'est un écosystème permettant de programmer des "petits ordinateurs", appelés ==microcontrôleurs== (uC, uC, MCU), afin de créer des objets interactifs.
Exemple : minuteurs de thermostats, télécommandes, microondes, art...
Langage : 
	pinMode(pin, mode) permet de dire si on utilise un port en entrée ou sortie.
	> pinmode(8, output)
	digitalWrite(pin, value) donne une valeur à un port ?
	arduino.cc/reference/
```c
void setup() {
    pinMode(10, OUTPUT);
}
void loop() {
   digitalWrite(10, HIGH);
   delay(50);
   digitalWrite(10, LOW);
   delay(100);
}
```

Solution pull-up / pull-down :
![[Pasted image 20231205152408.png]]
###### 07/12
Pour faire cela : pinMode(pin, INPUT_PULLUP)
digitalRead(pin) renvoie la valeur (HIGH ou LOW). 
```c
Serial.begin(115200)
Serial.print("Hello")
Serial.println(" World")
```
analogRead(pin) permet de lire l'int du pin analogue.
Pour analogWrite, on va sur les sortie informatiques avec un `~`, avec le PWM : ==Pulse Width Modulation==.
![[Pasted image 20231207114929.png]]
Un capteur numérique a besoin d'un "identifieur" pour savoir qui il est : Ce sont les protocoles. USB et HDMI (HDMI en a 4) sont des protocoles. 
Connaître la différence entre microcontrôleurs et m
ESP32 -> grande communauté IoT ; microcontrôleur. 

###### 08/12
[[ESP32]]

![[pin_map-2.png]]

###### Vidéo
Notre projet a été composé de façon à apprendre le hardware, et pour cela nous avons appris à utiliser un micro contrôleur tel qu'un Arduino Uno ou un esp32. Nous avons ensuite utilisé un lecteur de badge RFID RC522 et l'avons relié à un esp32. Cela nous a permis de faire un système rudimentaire mais complet d'un lecteur de badge qui nous a permis d'apprendre beaucoup de choses. Le plus difficile à dû être de coder un site et l'esp32 pour qu'ils interagissent ensemble, mais c'était très enrichissant. Et le plus intéressant à dû être la soudure de la puce rfid !