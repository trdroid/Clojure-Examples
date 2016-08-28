### Symbols

Symbols are names/identifiers in a Clojure program that represent "code" i.e. values or operations i.e. 
when the Clojure code (or a Clojure expression) is evaluated, the symbols are replaced by their value or they perform operations.

A symbol could optionally contain a namespace.

**Rules for a valid symbol**

A valid symbol identifier has the following requirements

* can contain any run of alphanumeric characters or any of the following characters: _=<>*!?$%&-+
* cannot start with a number
* cannot have a number succeed a +, - or . to avoid conflicting with *number* literals
* can contain a / ONLY in the middle as a separator between namespace and the identifier name

Valid Symbols: myvar, -myvar, <myvar>, my-var, my+var, mynamespace/myvar

Invalid Symbols: /myvar, -1myvar, +1myvar

### Constructing symbols

Symbols can be constructed from strings using the *symbol* function. The *symbol* function takes the name of the symbol and optionally the namespace of the symbol as arguments.

```scala
user=> (symbol "myvar")
myvar
user=> (symbol "mynamespace" "myvar")
mynamespace/myvar
```

### Reading and Evaluating

*Reading*

A Clojure program is read by a Clojure reader and is represented as a data structure. 
When a Clojure program is read, the symbols are read as is and are represented in the program data structure

*Evaluating*

When a Clojure program is evaluted, depending on whether the symbol represents a value or an operation, the symbol either is replaced with its value 
or performs an operation.

### Symbol as a literal

If a symbol has to be treated as a "literal value"/"data" but not as "code", it has to preceded by a single-quote character '. 

The Clojure reader identifies what follows a ' (single-quote character) as literal data but not as "code" to be evaluted.

In the following example, "myvar" is read and tried to be evaluated which results in an error as it is not bound to anything. 
However, preceding it with a ' allows it to be interpreted as a literal value/data.

```clojure
user=> myvar

CompilerException java.lang.RuntimeException: Unable to resolve symbol: myvar in this context, compiling:(C:\Users\droid\AppData\Local\Temp\form-init1231313053969201574.clj:1:1045)
user=> 'myvar
myvar
```

Consider another example where a symbol 'a' is defined in the namespace 'user' to refer to value 10 . 
When 'a' is entered at the REPL, it is read and evaluated to its value.
However, when it is preceded with a ', it is treated as a value and is not evaluated.

```clojure
user=> (def a 10)
#'user/a
user=> a
10
user=> 'a
a
```
