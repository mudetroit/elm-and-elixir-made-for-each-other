## Pattern matching
- Who doesn't like a good switch statements<!-- .element: class="fragment" -->
- Okay hands down<!-- .element: class="fragment" -->
- What if you could be told about your mistakes?<!-- .element: class="fragment" -->
- What if it could be more than a simple match?<!-- .element: class="fragment" -->


## Pattern matching - Elm
```
update msg model =
  case msg of
    Increment ->
      model + 1

    Decrement ->
      model - 1
```


## Pattern matching - Elixir
```
iex> case {1, 2, 3} do
...>   {4, 5, 6} ->
...>     "This clause won't match"
...>   {1, x, 3} ->
...>     "This clause will match and bind x to 2 in this clause"
...>   _ ->
...>     "This clause would match any value"
...> end
"This clause will match and bind x to 2 in this clause"
```


## Pattern matching - Elixir
```
iex> case {1, 2, 3} do
...>   {1, x, 3} when x > 0 ->
...>     "Will match"
...>   _ ->
...>     "Would match, if guard condition were not satisfied"
...> end
"Will match"
```


## Pattern matching - Elixir
```
iex> x = 1
1
iex> case 10 do
...>   ^x -> "Won't match"
...>   _ -> "Will match"
...> end
"Will match"
```


## Pattern matching
- Only really scratched the surface
- Better then polymorphic dispatch
