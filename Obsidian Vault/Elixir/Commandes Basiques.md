Une compilation des différentes commandes basiques.
[[Case, If, Cond]] pour le conditionnel en elixir et [[Quirks]] pour les étrangetés en elixir. [[Loops et Récursion]]. [[Modules, Fichiers et Fonctions]]. 

###### Division euclidienne
(// sur python) est div (a, b) où b agis sur a. 
div()
###### Modulo
(% sur python) est rem (a, b).
rem()

###### Round et Trunc
a = 3.58
trunc(a) prend l'int de la valeur, donc trunc(a) = 3
round(a) arrondi au plus proche, donc round(a) = 4

###### Booléens, is_integer, is_float, is_number, is_boolean
a = 1
is_integer(a) = true
is_float(a) = false
is_number(a) = true. is_number vérifie si la valeur est un int ou un float.
is_boolean(false) = true.
###### Atomes
Les Atomes sont des constantes qui ont pour valeur leur nom.
```elixir
IO.puts (:orange)
> orange
```
Cela renvoie la valeur "orange".
Ils sont souvent utilisés pour renvoyé l'état d'une opération ; on utilise souvent `:ok` ou `:error`.

###### Concatenate et #Strings
On utilise l'opérateur <> de cette façon
`foo = "hello" <> " world"`
Une interpolation ressemble à cela : 
```elixir
string = "world"
IO.puts ("hello #{strign}")
```
"hello world" a été output ici. Cela supporte tous les type de données.
`hello \n world` pour un avoir un line break.
On utilise `String.length(string)` pour avoir la taille d'un string et `String.upcase("hello")`  pour transformer hello en HELLO. 
String.split("hello world") renvoie ["hello, world"].
###### #Listes et Tuples
On utilise ++ et -- pour rajouter ou enlever des éléments précis aux listes une fois. Les variables sont immutables.
```elixir
[1, 2, 3] ++ [4, 5, 6]
> [1, 2, 3, 4, 5, 6]
[1, true, 2, false, 3, true] -- [true, false]
> [1, 2, 3, true]
```
Pour rajouter des éléments à `foo = [1, 2, 3]`, nous avons 2 choix :
```elixir
foo = foo ++ [4]
> [1, 2, 3, 4]
foo = [0 | foo]
> [0, 1, 2, 3, 4]
List.insert_at()
```
Pour prendre le premier élément, on utilise head : hd(foo) qui renvoie 0. Pour le reste, on récupère sa tail : tl(foo) qui renvoie [1, 2, 3, 4]. Pour la taille d'une liste, on utilise length(foo) qui revoie 5. 

a = {1, 2, 3}
Gérer les ==tuples== est plus simple car leur valeurs sont stockés de manière contiguë dans la mémoire. En outre, cela permet d'accéder et modifier des éléments à des indexes précis avec elem(a, 2) qui renvoie 3 et put_elem(a, 2, "boop"). 
`tuple_size(a)` renvoie 3.

Ainsi, comment choisir l'un ou l'autre ? Cela dépend de leur usage :
> - Chacune des valeurs d'une liste pointent vers le prochain élément. On dit qu'elle est linéaire. 
> > - Les opérations sur les listes sont donc lentes si on a besoin d'accéder aux dernières valeurs (Usage de length(a) ou encore la concaténation)
> - Dans un tuple, les opérations pour obtenir un élément ou la taille du tuple sont très rapides.
> > - Au contraire, rajouter ou modifier des éléments au tuple est gourmand en mémoire car cela requiert de créer un nouveau tuple.

Il faut donc bien gérer et prévoir les utilisations de chacun de ces types dans notre code si la mémoire doit le plus être sauvegardée.

###### ==Fonctions Anonymes==
Une fonction anonymes est délimitée par les mots-clés `fn` et `end`. Pour faire une fonction qui rajoute a à b, on peut donc avoir :
```elixir
add = fn a, b -> a + b end
add.(1, 2) # Renvoie 3 
```
On peut nester les fonctions anonymes :
```elixir
double = fn a -> add(a, a) end
double.(2) # renvoie 4
```
Pour les fonctions plus simples, on a une notation rapide :
```elixir
add_1 = &(&1 + 1)
add.(4) # Renvoie 5
```

###### Listes de mots-clés
Ce sont des arguments que l'on peut passer sous des fonctions afin d'accomplir certaines tâches précises au sein de ces fonctions. Par exemple :
```elixir
String.split("Mot1 et Mot2", " ")
> ["Mot1", "et", "Mot2"]
String.split("Mot1  et  Mot2", " ")
> ["Mot1", "", "et", "", "Mot2"]
String.split("Mot1  et  Mot2", " ", trim: true)
> ["Mot1", "et", "Mot2"]
```
La [[https://github.com/elixir-lang/ecto|libraire Ecto]] utilise cela pour ses queries SQL. Cela permet une meilleure lisibilité.
```elixir
query =
  from w in Weather,
    where: w.prcp > 0,
    where: w.temp < 20,
    select: w
```

###### Les maps en tant que dictionnaire
Les maps sont un type de données faisant la pair clé-valeur. 
```elixir
maps = %{:a => 1, 2 => :b}
maps[:a]
> 1
maps[2]
> :b
```
On peut assigner des variables aux valeurs par pattern matching : 
```elixir
maps = %{:a => 1, 2 => :b}
%{:a => a} = maps
a
> 1
```
On a une erreur MatchError si la valeur assignée n'existe pas dans la map.
Module Map est très utile utiliser les maps : 
```elixir
Map.get(%{:a => 1, 2 => :b}, :a)
> 1
Map.put(%{:a => 1, 2 => :b}, :c, 3)
> %{2 => :b, :a => 1, :c => 3}
Map.to_list(%{:a => 1, 2 => :b})
> [{2, :b}, {:a, 1}]
```
Si on souhaite qu'une map ne soit pas modifiable, on peut utiliser des atomes :
```elixir
maps = %{:name => "John", :age => 23}
> %{name: "John", age: 23}
maps.name
> "John"
```

==Structure de données imbriquées==
On peut utiliser les maps pour donner des données très rapidement ; à des utilisateurs par exemple :
```elixir
users = [
  john: %{name: "John", age: 27, languages: ["Erlang", "Ruby", "Elixir"]},
  mary: %{name: "Mary", age: 29, languages: ["Elixir", "F#", "Clojure"]}
]
users[:john].age
> 27
```
On peut aussi modifier une valeur précise de cette façon : 
```elixir
users = put_in users[:john].age, 31
[
  john: %{age: 31, languages: ["Erlang", "Ruby", "Elixir"], name: "John"},
  mary: %{age: 29, languages: ["Elixir", "F#", "Clojure"], name: "Mary"}
]
```
