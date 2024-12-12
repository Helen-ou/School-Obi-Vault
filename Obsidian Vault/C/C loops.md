Dans un loop, on a l'opération `++` qui incrémente de 1 la variable la précédent.
Exemple d'un for loop

```c
#include <stdio.h>

int main() {
	
	for(int i = 0; i < 10; i++) { // Répète 10 fois
		printf("beep boop\n");
	}
	
	for(int i = 0; i < 10; i+= 2) {
		printf("%d\n", i);
	}
	
	return 0;
}
```
Exemple d'un loop while et do while.

```c
#include <stdio.h>

int main() {
	int exemple = 16;
	int i = 0;
	while(1) {
		if(i == exemple) {
			printf("ENFIN\n");
			break;
		} else {
			printf("Encore %d fois ?\n", exemple - i);
			continue;
		} 
	}

	do{
		printf("Je m'exécute une seule fois");
	}while(0);
	
	return 0;
}
```