## Developer ergonomics
- Java <!-- .element: class="fragment" -->
- Ruby <!-- .element: class="fragment" -->


## Java
- Awesome platform <!-- .element: class="fragment" -->
- Relatively simple syntax <!-- .element: class="fragment" -->
- Appeals strongly to large enterprises (chosen by management) <!-- .element: class="fragment" -->


## Ruby
- Powerful language features <!-- .element: class="fragment" -->
- Relatively large number of language features <!-- .element: class="fragment" -->
- Appeals strongly to small start ups (chosen by developers) <!-- .element: class="fragment" -->


## Let's look at some trends
- Microservices <!-- .element: class="fragment" -->
- Docker <!-- .element: class="fragment" -->
- Cloud based infrastructure <!-- .element: class="fragment" -->


## What can we learn
- Trading deployment complexity for development speed <!-- .element: class="fragment" -->
- Trading hosting costs for flexibility <!-- .element: class="fragment" -->

- Generally speaking making life easier for developers outweighs increated costs elsewhere <!-- .element: class="fragment" -->


## So what do Elixir and Elm give us here?
- Awesome error messaging <!-- .element: class="fragment" -->
- The Elm Architecture (TEA) <!-- .element: class="fragment" -->
- OTP/BEAM <!-- .element: class="fragment" -->


## Error messaging - The bad
```
<interactive>:2:1:
    Could not deduce (Num (a0 -> t))
      arising from the ambiguity check for ‘it’
    from the context (Num (a -> t), Num a)
       bound by the inferred type for ‘it’: (Num (a -> t), Num a) => t
       at <interactive>:2:1-4
    The type variable ‘a0’ is ambiguous
    When checking that ‘it’
      has the inferred type ‘forall a t. (Num (a -> t), Num a) => t’
    Probable cause: the inferred type is ambiguous
```


## Error messaging - it really does matter
- Compiler errors are a great way to explain to someone new what they did wrong <!-- .element: class="fragment" -->
- They can reduce time wasted on simple mistakes<!-- .element: class="fragment" -->


## Error messaging - More bad
```
$test = 1
echo $test;

> Parse error: parse error in c:test.php on line 2
```


## Error messaging - The okay
```
iex> :foo + 1
** (ArithmeticError) bad argument in arithmetic expression
     :erlang.+(:foo, 1)
```


## Error messaging - The good
![Elm error](img/elm-error.png)


## Error messaging - The good
![Elm error](img/elm-error-2.png)


## Error messaging - Fin
- Error messaging is not the time for a compiler to be pedantically correctly <!-- .element: class="fragment" -->
- A good language/compiler will give helpful errors<!-- .element: class="fragment" -->
- Include the more specific reasoning after the helpful bits<!-- .element: class="fragment" -->


## The Elm Architecture
![The Elm architecture](img/elm-architecture-overview-diagram.svg)


## The Elm Architecture
- Puts some limits on where Elm can be used<!-- .element: class="fragment" -->
- Situates Elm well for its intended use<!-- .element: class="fragment" -->
- Helps developers fall into the "pit of success"<!-- .element: class="fragment" -->


## Elixir OTP/Beam
- Focus on solid boundaries and independent apps <!-- .element: class="fragment" -->
- Don't try to save it when there is an exception, let it crash and restart<!-- .element: class="fragment" -->
- Supervisors and app trees <!-- .element: class="fragment" -->
- Like a microservice architecture without a lot of the requisite pain <!-- .element: class="fragment" -->
