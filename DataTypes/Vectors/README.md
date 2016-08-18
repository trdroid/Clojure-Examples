### Vectors

A vector is collection type that can store a series of elements where each element can be indexed by number. A vector literal is represented using square brackets.


**Vectors vs Lists**

*Similarities*

* heterogeneous types

*Differences*

* Vectors provide fast random access to its elements by allowing its elements to be accessed with a number index.
* Vectors evaluate each item in order.
* Functions and Macros do not operate on the vector itself.


**Creation**

A vector can be created using the *vector* function that Clojure provides or by using a vector literal.

**vector**

```clojure
user=> (vector 1 2 3)
[1 2 3]
user=> (vector 1 2 "text" 3 4)
[1 2 "text" 3 4]
user=> (vector 3 4 5)
[3 4 5]
user=> (vector 3 4 :symbol "string" 5 6)
[3 4 :symbol "string" 5 6]
```

**Literal**

```clojure
[1 2 3 4]
[1 :symbol "text" 2 3 4]
```

**Creating vector variables**

The following creates a vector using the *vector* function and assigns it to 'myVector'

```clojure
user=> (def myVector (vector 1 2 3))
#'user/myVector
user=> myVector
[1 2 3]
```

The following creates a vector using its literal syntax and assigns it to 'myV'. Notice how the vector literal is used directly and is not prefixed by a quote like for a list literal.

```clojure
user=> (def myV [1 2 :a :b 3 4 "str"])
#'user/myV
user=> myV
[1 2 :a :b 3 4 "str"]
```

**Accessing elements**

Clojure provides *get* and *nth* functions to access elements of a vector.

```clojure
user=> (vector 1 2 3 4 5 :a :b :c)
[1 2 3 4 5 :a :b :c]
user=> (get *1 1)
2
user=> (get *1 0)
nil
```

Notice how the last output is *nil*, as *1 now points to 2 instead of the vector

```clojure
user=> (def myVec [1 2 3 :a :b :c "a" "b" "c"])
#'user/myVec
user=> myVec
[1 2 3 :a :b :c "a" "b" "c"]
user=> (get myVec 0)
1
user=> (nth myVec 2)
3
```
