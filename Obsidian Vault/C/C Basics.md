Les bases du C, document pour se référer par rapport aux différences entre les langages.
Les [[C loops|boucles]] ont leur note.

###### Types de variables :

| Nom dans le code | Description |
| ---- | ---- |
| int | Entier signé par défaut, limites à -2^31 et 2^31 |
| char | Stocke un charactère unique |
| char[] | Array (liste) de charactères ; string |
| float | Nombre à virgule signé par défaut, limites à  |

###### Spécificateurs de format et choses utiles pour printf : 

| Spécificateur | Utilisé pour |
| ---- | ---- |
| \n | Va à la ligne, pas fait automatiquement par printf |
| %c | Un seul charactère |
| %s | Une chaîne de charactères |
| %d | Un nombre décimal en base 10 (int) |
| %f | Un nombre float |
| %e | Un nombre float en notation scientifique |
Exemple dans du code :
```c
#include <stdio.h> // Input/Output
#include <stdbool.h> // Booléens

int main() {
	char unique = "c";
	char STRING[] = "owo"; // uppercase par convention
	int puissance32 = 2147483647;
	const bool vrai = true; // Variable inchangeable
	printf("Charactère unique : %c ; String : %s ; Entier naturel : %d ; Booléen : %d\n", unique, STRING, puissance32, vrai)

	

	return 0; // Fin fonction main
}
```
###### Pour demander un input à l'utilisateur :

```c
#include <stdio.h>
#include <string.h> 
// Pour enlever le \n ajouté automatiquement par fgets

int main() {
	int age; // initialisation
	char nom_prenom[25];
	
	printf("Quel est ton nom et prénom ? ");
	fgets(nom_prenom, 25, stdin); 
	// variable, bytes alloués, standardinput
	nom_prenom[strlen(nom_prenom) - 1] = "\0";

	printf("\nQuel âge as-tu ? : "); // question
	scanf("%d", &age); // input 

	printf("\nTu t'appelles %s", nom_prenom);
	printf("\nTu as %d ans", age); // exemple
	return 0;
}
```
###### Pour la librairie <math.h> :

```c
#include <stdio.h>
#include <math.h>

int main() {
	double puissance = pow(2, 4); // 2^4 = 16
	double racine = sqrt(16); // 4
	int arrondire = round(3.14); // 3
	int arrondire_sup = ceil(3.14); // 4
	int arrondire_min = floor(3.14); // 3
	double distance_abs = fabs(-56); // 56
	
	return 0;
}
```
###### Pour vérifier un grand nombre d'égalités avec switch:

```c
#include <stdio.h>

int main() {
	char note = "D";
	switch(note) { 
		case "A":
			printf("Parfait!");
			break; // sortir du switch
		case "B":
			printf("Bien joué !")
			break;
		case "C":
			printf("Travaille plus la prochaine fois");
			break;
		case "D":
			printf("Irrécupérable !")
			break;
		case "F":
			printf("Touche le fond mais continue de creuser")
			break;
		default:
			printf("La note rentrée n'est pas correcte !")
	}
}
```
###### Les opérateurs logiques

| Opérateurs logiques | En C |
| ------------------- | ---- |
| and, et             | &&   |
| or, ou              | \|\| |
| not, non            | !    |

###### Les fonctions :

```c
#include <stdio.h>

void super_nom_evocateur(char string[]) {
	printf("%s", string);
}

int main() {
	super_nom_evocateur("ÒwÒ");
	return 0;
}
```
###### Quelques outils intéressants pour les strings :

```c
#include <stdio.h>
#include <string.h>

int main() {
	char string1[] = "strings";
	char string2[] = " are neat";
	
	strupr(string1); 
	// string1 = "STRINGS", strlwr lowercase
	strcat(string1, string2); 
	/* string1 = "strings are neat"
	strncat(_, _, n) va concaténer n charactères */
	strcpy(string1, string2); 
	/* string1 = " are neat"	
	strncpy(_, _, n) copies n charactères */


	int length = strlen(string1);
	
	return 0;
}
```