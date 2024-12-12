**Trop Long ; Pas lu** : J'ai créé un challenge dans ma spécialité de Reverse Engineering.

En cybersécurité, la plupart des mes camarades montent en compétences grâce à des plateformes : RootMe, HTB et bien d'autres.
Ces plateformes, que font-elles ? Elles donnent accès à des challenges qui permettent d'apprendre en autodidacte de nouvelles compétences ; je les utilise aussi. 

Mais ce que je trouve le plus intéressant, c'est de créer ces challenges. Étant donné que le Reverse-Engineering est ma spécialité préférée, c'est ce que j'ai fait. Et je vais parler aujourd'hui de cela : Le process de création d'un challenge, ses phases et ses difficultés.

Tout d'abord, il faut prévoir : Quel langage de programmation, quelles infrastructure, quelles idées intéressantes pour faire apprendre..
En deux points clés, voici les deux choix qui ont été les plus important :
- D'abord, le but est de faire apprendre quelque chose aux challengers, aller au coeur du langage ordinateur est intéressant. Le langage de programmation a été choisi pour cela : Le C qui permet d'être très proche du code assembleur, de faire des changements facilement et rapidement au code (Et que je connais mieux que la programmation en assembleur..).
- Puis on utilise le langage pour coder une idée intéressante. D'abord, je pensais utiliser le moment précis de compilation du code comme biais pour obtenir un mot de passe. Explorer cette idée à été très intéressante, mais trop simple à Reverse (ou tout du moins dans ma version). Faisant une impasse avec cette voie, @Robin GRZYWACS m'a aidé à trouver l'idée d'utiliser une création de nombres aléatoires prévisible pour décoder un mot de passe.

Ensuite et pendant, phase de création : 
> On créé, on test, on reverse et on modifie le code peu à peu pour atteindre l'objectif.

