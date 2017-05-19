## Immutability
- Things don't change once they are created <!-- .element: class="fragment" -->
- Techniques are developing that make immutability easier <!-- .element: class="fragment" -->


## Immutability - Why do we need it?
- Concurrent programming <!-- .element: class="fragment" -->
- We all suck at understanding mutable programs<!-- .element: class="fragment" -->

- Done correctly, it can be hidden from us <!-- .element: class="fragment" -->


## Single threaded performance
![Microprocessor trends](img/35-years-of-microprocessor-trends.jpg)


## Immutability
- Concurrent programming
- Actor model <!-- .element: class="fragment" -->


## Actor model
![Actor model](img/actor-model.png) <!-- .element: width="800" height="400" -->


## Actor model - Elixir
```
defmodule Producer do
  use  ExActor

  defcast produce, state: consumer do
    :timer.sleep(100)
    value = :random.uniform(100)
    consumer.consume(value)
    IO.puts "produced #{value}"
  end
end
```


## Actor model - Elixir
```
defmodule Consumer do
  use  ExActor

  defcast consume(value) do
    :timer.sleep(200)
    IO.puts "                consumed #{value}"
  end
end
```


## Actor model - Elixir
```
produced 45
produced 73
                consumed 45
produced 95
produced 51
                consumed 73
produced 32
                consumed 95
                consumed 51
                consumed 32
```


## Immutability
- Concurrent programming techniques are required
- Actor model
- Unidirectional data flow <!-- .element: class="fragment" -->


## Unidirectional data flow
![Unidirectional data flow](img/Unidirectional-data-flow.png)


## Unidirectional data flow - Elm
```
type Msg = Increment | Decrement

update msg model =
  case msg of
    Increment ->
      model + 1

    Decrement ->
      model - 1

view model =
  div []
    [ button [ onClick Decrement ] [ text "-" ]
    , div [] [ text (toString model) ]
    , button [ onClick Increment ] [ text "+" ]
    ]
```


## Immutability - Elm
```
point =                         -- create a record
  { x = 3, y = 4 }

List.map .x [point,{x=0,y=0}]   -- field access function

{ point | x = 6 }               -- update a field

{ point |                       -- update many fields
    x = point.x + 1,
    y = point.y + 1
}
```


## Pointing us towards time
- Unidirectional data flows push us towards time being first class <!-- .element: class="fragment" -->
- No longer think about a model is, but what it looks like after something <!-- .element: class="fragment" -->
- Moving towards streams of data <!-- .element: class="fragment" -->
