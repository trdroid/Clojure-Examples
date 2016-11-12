# Functions

### Properties

Clojure, derived from Lisp, is a functional language which treats functions as first class elements, which implies

* Functions can be created dynamically at runtime
* Functions can be accepted as arguments by other functions
* Functions can be returned as values from other functions
* Functions can be stored as elements/values in other data structures, like lists

### Defining functions

In Clojure, functions are defined using the *defn* macro, the syntax of which is as follows:

```clojure
(defn <function name>
  doc-string?
  metadata-attr-map?
  [parameter-list*]
  prepost-conditions-map?
  body-expressions*)
```

The symbols suffixed with a '?' are optional.

**Underneath the hoods**

The *defn* form 

* expands to a *def* to create a *var* with the name \<function name\> and 
* creates a function with *fn* macro
* points the created \<function name\> var to the function

**Defining a basic function**

```clojure
user=> (defn add [num1 num2]
  #_=>  (+ num1 num2))
#'user/add
user=> (add 5 10)
15
```
