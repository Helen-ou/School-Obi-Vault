Case est une suite d'essais qui recherche des patterns et va exécuter une commande.
```elixir
	case {1, 2, 3} d
  {4, 5, 6} ->
    "Rien ne va se passer"
  {1, x, 3} when x > 0 ->
    "Va renvoyer ce string, x deviens 2"
  _ ->
    "Match tout le temps, renverrait ce string si       fait plus tôt!"
end
```
La clause `when` permet de confirmer la clause seulement si x est positif dans ce cas (donc oui). 
Si on souhaite utiliser une condition case ==contre== une variable, on utilise `^variable1 -> "On a comparé la condition à la variable variable1"`. 
A noter qu'une erreur est renvoyée si aucune clause vraie n'est trouvée.
Moins utile que Cond qui est...
###### Cond
C'est l'équivalent d'une suite de if-ifelse-ifelse.. statements. 
```elixir
cond do
  2 + 2 == 5 ->
    "Pas vrai"
  2 * 2 == 3 ->
    "Non plus"
  1 + 1 == 2 ->
    "Mais ça oui!"
  true -> "Toujours vrai"
end
```
Comme une erreur est renvoyée si aucune clause n'est vraie, on peut souvent utiliser une clause toujours vraie. Une clause toute seule est considérée comme vraie si elle n'est pas nil ou false.
###### If/Unless
Classique if/else avec un mix de valeurs locales :
```elixir
x = "boop beep ?"
x = if 1 == 1 do
	"beep boop !"
else 
	"1 vaut toujours 1 donc personne ne me verra        jamais :("
unless 1 == 2 do
	"Je ne serai jamais vu non plus :("
```
A noter que les valeurs renvoyées sont locales.