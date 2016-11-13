# Arity

The *arity* of a function is the number of parameters it accepts. 

### Function Overloading

Funtions in Clojure can be overloaded on arity. 
A function can be defined with various forms and the body of the function that executes depends on the number of arguments the function is called with.

**General form**

Consider a general form of a function called "function-name" defined with two arities, one with arity 2 and the other with arity 3.

```clojure
(defn function-name
  ([arg1 arg2]         function-body-1)
  ([arg1 arg2 arg3]    function-body-2)
)
```

Notice that each argument + function-body pair is enclosed in a list.

The following call executes "function-body-1" 

```clojure
(function-name argX argY)
```

The following call executes "function-body-2" 

```clojure
(function-name argX argY argZ)
```

Consider a function "add" with two arities, 2 and 3.

```clojure
user=> (defn add
  #_=>  ([num1 num2] (+ num1 num2))
  #_=>  ([num1 num2 num3] (+ (+ num1 num2) num3))
  #_=> )
#'user/add
user=> (add 5 10)
15
user=> (add 5 10 15)
30
```

**Calling another arity version of the function from any other arity**

The function body of "add" with arity 3 can be redefined to use the version of "add" with arity 2, as shown below

```clojure
user=> (defn add
  #_=>  ([num1 num2] (+ num1 num2))
  #_=>  ([num1 num2 num3] (add (add num1 num2) num3))
  #_=> )
#'user/add
user=> (add 5 10)
15
user=> (add 5 10 15)
30
```

Reformatting ...

```clojure
user=> (defn add
  #_=>  ([num1 num2]
  #_=>   (+ num1 num2))
  #_=>  ([num1 num2 num3]
  #_=>   (add (add num1 num2) num3))
  #_=> )
#'user/add
user=> (add 5 10)
15
user=> (add 5 10 15)
30
```
