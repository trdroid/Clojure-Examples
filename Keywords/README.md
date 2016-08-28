### Keywords

Symbols in Clojure can be treated as data by preceding them with a ' (single-quote character). 
Clojure offers a type called *keyword* as a shorthand for representing symbols as data but not as code.

A *keyword* always evalutes to itself and never references or evaluates to another value.

**Literal Syntax**

The literal syntax of a keyword is prefixed by a colon ':', but the colon is not part of the name itself. 

Valid keywords: 

:NameOfMyKeyword

:myvar, :+myvar, :->myvar

:-, :+, :?, :5

**Constructing a keyword**

A keyword can be constructed by preceding a symbol with a ':' or by using the *keyword* function.

*Using the keyword function*

```clojure
user=> (keyword "myvar")
:myvar
```

### Usages

Keywords are widely used as 

* keys in hash maps 
* enumeration values
