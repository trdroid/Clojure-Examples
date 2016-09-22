# Atoms

An *atom* is a construct offered by Clojure which allows for modifications of mutable data in the following ways

* synchronous &
* independent 

### Creating Atoms


### Mutating Atoms


### In comparison

**Atom vs Agent**

The updates to *atoms* happen 

* synchronously &
* immediately

whereas, the updates to *agents* happen 

* asynchronously
* at some point in future

**Atom vs Ref**

The changes to atoms cannot be coordinated and are independent from each other. All the changes either happen or none happens at all.
