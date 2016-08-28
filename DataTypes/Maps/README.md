# Maps

A map is a collection of key-value pairs. The keys could be any kind of object, but a common pattern is to use symbols for keys. 
Maps are immutable like any data structure in Clojure.

**Properties**

In Clojure, maps are 

* immutable

### Creation

Clojure provides two map implementations

* Array Map
    * keys and values are stored in sorted order
    * Lookups are performed by scanning rather than hashing (so lookups are faster for smaller maps)
* Hash Map
    * Uses hashing to store key-value pairs and to perform lookups

**Using literal syntax**

Maps can be created using the literal syntax as shown below

```clojure
user=> (def sample-map {:p 10 :q 20 :r 30})
#'user/sample-map
```

When a map is created using the literal syntax, the implementation Clojure chooses to represent the map depends on the size of the map.

Smaller maps (~<= 10 keys) are represented using the Array Map implementation. 
Adding more keys to such a map would eventually result in the switching to an Hash Map implementation. 
However, removing keys after a switch to a Hash Map implementation does not result in switching back to an Array Map implementation.

**Using functions**

Clojure provides the functions *hash-map* and *array-map* to create maps. 
The *hash-map* function always represents a map using a Hash Map, whereas the *array-map* function always represents a map using an Array Map.

```clojure
user=> (def p-map (hash-map :p 10 :q 20 :r 30))
#'user/p-map
user=> p-map
{:q 20, :r 30, :p 10}
user=> (array-map :p 10 :q 20 :r 30)
{:p 10, :q 20, :r 30}
```

### Retrieving values

```clojure
user=> (sample-map :p)
10
user=> (:p sample-map)
10
```

### Functions that operate on a map



