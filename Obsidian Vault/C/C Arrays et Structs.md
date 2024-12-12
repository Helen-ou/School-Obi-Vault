#### Les tableaux en C.

```c
#include <stdio.h>

int main() {
	double notes[] = {5.0, 10.0, 15.0, 18.5};
	
	printf("La note de l'élève 2 est : %.1lf\n", notes[1]);
	int i;
	int longeur_tableau = sizeof(notes) / sizeof(notes[0]);
	
	/* sizeof() renvoie la longueur en bytes d'une variable, donc on divise par la taille d'un élément. Ne fonctionne que si tous les éléments du tableau sont du même type */
	
	for(i; i < longeur_tableau; i++) {
		printf("La note de l'élève %d est %lf\n", i + 1, notes[i]);
	}
	
	return 0;
}
```
Pour une matrice, le chiffre **3** dénote ici la taille maximale d'un des sous tableaux et est obligatoire. On peut faire pareil pour le premier [] mais cela n'est pas obligatoire.
```c
int matrice[][3] = {{1, 2, 3}, {4, 5, 6}};
```



#### Les structs

Les structs sont TRÈS SIMILAIRES aux classes, mais ceux-ci ne possèdent pas de méthode.

```c
#include <stdio.h>
#include <string.h>

struct Joueur {
	char nom[25];
	int score;
};

// typedef() donne un "surnom" à un type de données
// Surtout utile pour les structs

typedef struct {
	char menu[25];
} Jeu;

int main() { 
	// initialisation jouer 1
	struct Joueur joueur1;
	struct Joueur joueur2 = {"Nope", 3};

	strcpy(joueur1.nom, "ÒwÒ");
	joueur1.score = 6;

	printf("Le score de %s est %d\n", joueur1.nom, joueur1.score);
	printf("Le score de %s est %d\n", joueur2.nom, joueur2.score);


	Jeu ecran_titre = {"Commencer la partie"};
	printf("%s", ecran_titre.menu);
	return 0;
}
```


|  | 3 joueurs | 4 joueurs | 5 joueurs | 6 joueurs | 7 joueurs |
| ---- | ---- | ---- | ---- | ---- | ---- |
| Shogun | 2 | 1 | 1 | 1 | 1 |
| Samuraï |  | 2 | 1 | 2 | 1 |
| Ninja | 1 | 1.5 | 1 | 1 | 1 |
| Ronin |  |  | 2 | 3 | 3 |
