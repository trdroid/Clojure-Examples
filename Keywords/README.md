### Keywords

Symbols in Clojure can be treated as data by preceding them with a ' (single-quote character). 
Clojure offers a type called *keyword* as a shorthand for representing symbols as data but not as code.

A *keyword* always evalutes to itself and never references or evaluates to another value.

### Constructing a keyword

A keyword can be constructed by preceding a symbol with a ':' or by using the *keyword* function.

Valid keywords: 

:myvar, :+myvar, :->myvar, :-, :+

```clojure
user=> (keyword "myvar")
:myvar
```
