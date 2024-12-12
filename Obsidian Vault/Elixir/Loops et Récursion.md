### Par Récursion
En élixir, il n'y a pas de for loop. On a donc deux moyens de créer des boucles : la récursion et le module Enum.
Par récursion :
```elixir
defmodule Recursion do
  def print_multiple_times(msg, n) when n > 0 do
    IO.puts(msg)
    print_multiple_times(msg, n - 1)
  end

  def print_multiple_times(_msg, 0) do
    :ok
  end
end

Recursion.print_multiple_times("Hello!", 3)
> Hello!
> Hello!
> Hello!
:ok
```
On output ici 3 fois "Hello!" puis utilisons l'atome `:ok` pour confirmer la fin de la boucle.
Par Enum :
==A noter plus tard une fois Enum vu !==

Par algorithme de réduction dans une liste  : 
```elixir
defmodule Math do
  def sum_list([head | tail], accumulator) do
    sum_list(tail, head + accumulator)
  end

  def sum_list([], accumulator) do
    accumulator
  end
end

IO.puts Math.sum_list([1, 2, 3], 0)
# sum_list [1, 2, 3], 0
# sum_list [2, 3], 1
# sum_list [3], 3
# sum_list [], 6
> 6
```
### Par la classe Enum
On peut utiliser la classe #Enum avec des fonctions anonymes. On a les fonctions :
```elixir
Enum.each([1, 2, 3], fn x -> IO.puts(x) end)
> 1 \n 2 \n 3 \n
Enum.map([1, 2, 3], fn x -> x * 2 end)
> [2, 4, 6]
Enum.map(%{1 => 2, 3 => 4}, fn {k, v} -> k * v end)
> [2, 12]
Enum.reduce(1..3, 0, &+/2)
> 6
even_numbers = Enum.filter([1, 2, 3, 4], fn x -> rem(x, 2) == 0 end)
IO.puts even_numbers
> [2, 4]
has_even = Enum.any?([1, 3, 5, 6], fn x -> rem(x, 2) == 0 end)
IO.puts has_even
> true
unique_list = Enum.uniq([1, 2, 2, 3, 4, 4, 5])
IO.puts unique_list
> [1, 2, 3, 4, 5]
```
==Enum.each== : Applique une fonction à chaque élément de l'énumérable.
==Enum.map== : Applique une fonction à chaque élément de l'énumérable et renvoie une liste des résultats.
==Enum.reduce== : Applique une fonction pour agréger les éléments de l'énumérable.
==Enum.filter== : Retourne une nouvelle liste contenant uniquement les éléments qui satisfont une condition.
==Enum.any? et Enum.all?== : Vérifient si au moins un élément (any) ou si tous les éléments (all) de l'énumérable satisfont une condition. Renvoie un booléen.
==Enum.uniq== : Retourne une nouvelle liste en supprimant les éléments en double de l'énumérable.
On peut aussi faire une #range facilement : `1..3` renvoie [1, 2, 3]
Pour un code plus clair, et propre on peut utiliser le ==pipe operator== `|>`, qui prend la valeur à sa gauche et la passe en premier paramètre à droite :
```elixir
odd? = fn x -> rem(x, 2) != 0 end
Enum.sum(Enum.filter(Enum.map(1..100_000, &(&1 * 3)), odd?))
> 7500000000

# Deviens cela :
odd? = fn x -> rem(x, 2) != 0 end
1..100_000 |> Enum.map(&(&1 * 3)) |> Enum.filter(odd?) |> Enum.sum()
> 7500000000
```
