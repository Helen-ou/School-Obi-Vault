###### Modules
`String.split` est un module et une fonction : le module String et la fonction split. Nous allons donc créer ces modules. On utilise `defmodule` et la première lettre doit être en majuscule.
```elixir
defmodule Monsupermodule do
	defp rajouter(a, b) do
		a + b
	end
	def doubler(a) when is_integer(a) do
		rajouter(a, a)
	end
end
Monsupermodule.doubler(2)
> 4
```
Dans une fonction, on peut donner une valeur par défaut aux arguments de cette façon :
`def fonction(a, b  \\ 0)`. Ici, b à pour valeur par défaut 0.

Avant de continuer, comment utiliser ces modules dans notre code? On peut compiler un fichier elixir .ex avec la commande : 
`$ elixirc fichier.ex`. Pour coder plus simplement et tester, on peut utiliser l'extension .exs qui ici est en langage interprété. 

###### Fonctions et Fonctions Anonymes