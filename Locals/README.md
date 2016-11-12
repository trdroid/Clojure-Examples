# Locals

The *let* form in Clojure can be used to create and define the scope of *locals*.

A *local* is defined by 

* the *let* keyword 
* followed by a vector that defines bindings
* followed by any number of expressions, which makes up the body of the *local*

```clojure
user=> (let [length 5
  #_=>       breadth 10
  #_=>       area (* length breadth)]
  #_=>  (println "area = " area)
  #_=>  area
  #_=> )
area =  50
50
```

**Result**

The body of a *local* can contain any number of expressions, which are all evaluated, but only the result of the last expression evaluated is returned.

**Similarities with the *do* form**

The body of a *local* can be considered to contain an *implicit do* as it can contain any number of expressions, 
which are all evaluated, but only the result of the last expression evaluated is returned, just like a how a *do* block is evaluated.

