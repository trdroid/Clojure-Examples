# Blocks

In Clojure, a series or a block of s-expressions can be aggregated to be treated as one expression using the *do* form. 

```clojure
user=> (if (< 5 10)
  #_=>  (do
  #_=>   (def x 20)
  #_=>   (def y 15)
  #_=>   (- x y)
  #_=>  )
  #_=> )
5
```

**Value**

All the expressions in a block are executed, but only the value of the last expression evaluated is returned . 

Example

```clojure
user=> (if (< 5 10)
  #_=>  (do
  #_=>   (def x 20)
  #_=>   (def y 15)
  #_=>   (+ x y)
  #_=>   (- x y)
  #_=>  )
  #_=> )
5
```

The expression (+ x y) in the block is executed but the value of it is discarded.

**Side Effects**

If a higher-order form accepts only a single s-expression and certain side effects are desired, then a *do* form can be used to encapsulate the side effects while it can be passed to that higher-order form.




