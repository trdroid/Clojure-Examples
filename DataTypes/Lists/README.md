### Lists

Lists are the classic collection data structure that is offered by Clojure (and most commonly by other Lisp language; as the name Lisp itself comes from *list processing*). Lists in Clojure are singly linked lists which implies that

* elements can only be added or removed from the front of the list
* multiple lists can share the same tail of the list (which makes it an immutable data structure)

**Literal**

A list literal is written with parentheses.

```clojure
()
(1 2 3)
```

NOTE: An empty list is not the same as *nil*

**Heterogeneity**

A list can contain items of any type, including other collecion types.

```clojure
(1 2 3)
(1 (a b c) 2 3 4)
(1 2 :symbol text)
```

**list**

Clojure provides the *list* function to create a list and a *list?* function to test for list types. 

```sh
user=> (list 1 2 3 4 5)
(1 2 3 4 5)
user=> (list? *1)
true
user=> (def l (list 8 9 10))
#'user/l
user=> (list? l)
true
```

Clojure provides the following functions to operate on a list

**count** 

Use the *count* function to count the number of items in constant time.

```sh
user=> (count myList)
3
```

**peek & pop**

Clojure provides the functions *peek* and *pop*. 

*peek* returns the head of the list, whereas *pop* returns the tail of the list.

```sh
user=> (def myList (list 1 2 3))
#'user/myList
user=> (peek myList)
1
user=> (pop myList)
(2 3)
user=> myList
(1 2 3)
```

**conj**

The *conj* function is a generic function to add an item to a collection. It does it in the fastest way possible for that collection.
For a list, it adds an item at the front of the list.

The following usage of the *conj* function creates a new list with the supplied argument value added to it

```sh
user=> (conj (list 1 2 3) 4)
(4 1 2 3)
user=> myList
(1 2 3)
user=> (conj myList 10)
(10 1 2 3)
user=> myList
(1 2 3)
```

If multiple arguments are provided, then the values are added in the order they are provided

```sh
user=> (conj (list 1 2 3 4) 5 6 7)
(7 6 5 1 2 3 4)
user=> (conj (conj (conj (list 1 2 3 4) 5) 6) 7)
(7 6 5 1 2 3 4)
```

### How Lists are evaluated

Consider the following way of assigning a list to a variable, which results in an exception because of the way lists are evaluated. 

```sh
user=> (def myList (1 2 3))

CompilerException java.lang.ClassCastException: java.lang.Long cannot be cast to clojure.lang.IFn, compiling:(form-init7490360418716086003.clj:1:13)

```

When a Clojure reader reads and parses a list, it evaluates it by treating the first symbol as a function or a macro or a special operator. If the first symbol is a function then it evaluates the rest of the items/expressions and passes their values as arguments to that function. If the first symbol is a macro or a special operator, the rest of the items/expressions are processed as defined by the macro/operator and are not necessarily evaluated.

For example, when the expression (+ 1 2 3 4), which is a list, is entered at an REPL prompt, it is read and parsed by the Clojure reader, which then evaluates it by calling the + function with the arguments 1, 2, 3 and 4.

Similarly, Clojure tried evaluating the list literal (1 2 3) like all lists by attempting to call a function '1' and passing it arguments 2 and 3, which resulted in an exception.

In order to specify to Clojure not to treat the list literal (1 2 3) as code but instead as data, prefix the list literal with a quote as shown below

```sh
user=> (def myList '(1 2 3))
#'user/myList
user=> myList
(1 2 3)
```

**Lists for Clojure code**

Clojure code is represented using Clojure data structures. List is an essential data structure used to represent expressions in Clojure code. Each expression in the code is a list, which can contain other data structures like vectors.
