# Conditionals

A conditional form in Clojure can be used to conditionally execute or not execute code.

### *if* Form

*if* is a special form that the Clojure language implements internally as a special case. 
Using the special *if* form and the macro system, Clojure implements all other conditional forms as macros. 

**General *if* form**

```clojure
(if condition consequent alternative)
```

```clojure
user=> (if (> 5 10) "5 > 10" "5 < 10")
"5 < 10"
```

```clojure
user=> (if (> 5 10)
  #_=>  "5 > 10"
  #_=>  "5 < 10")
"5 < 10"
```

**General *if* form**

```clojure
(if condition consequent)
```

```clojure
user=> (if (< 5 10) "5 < 10")
"5 < 10"
```

```clojure
user=> (if (> 5 10) "5 > 10")
nil
```

### *if-not* Macro


