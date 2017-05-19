## The pipe operator
|>


## The pipe operator
![Pizza](img/pizza.png)


## Function composition
```
var names = ['Jim', 'Jane', 'Jem', 'Igor', 'Kate'];

var sortedNames = names.sort();
return sortedNames.join(',');
```


## Function composition
```
// Method chaining
var names = ['Jim', 'Jane', 'Jem', 'Igor', 'Kate'];

return names
  .sort()
  .join(',');
```


## In Elm
```
viewNames1 names =
  String.join ", " (List.sort names)
```


## In Elm - Pipe operator
```
viewNames2 names =
  names
    |> List.sort
    |> String.join ", "
```


## In Elixir
```
Enum.join(Enum.sort(names), ",")
```


## In Elixir - Pipe operator
```
names
  |> Enum.sort
  |> Enum.join(",")
```


## Do we really care?
- Code looks closer to what we are trying to say <!-- .element: class="fragment" -->
- It takes longer to read code then write it <!-- .element: class="fragment" -->
- Optimize for reading <!-- .element: class="fragment" -->


## Function composition is important
- Is-a vs Has-a <!-- .element: class="fragment" -->
- Small consumable pieces <!-- .element: class="fragment" -->
- The promise of software<!-- .element: class="fragment" -->


## Hardware vs software
Hardware: Comparatively beneficial to design up front, changing purpose is hard

Software: Comparatively less benefit from upfront design, easier to change later


## Changing design is easier with composition
- Large monolithic systems fight change <!-- .element: class="fragment" -->
- This is why microservices have gained popularity <!-- .element: class="fragment" -->
