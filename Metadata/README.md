# Metadata

Clojure allows metadata (data about data) to be added to various objects without changing their value. 
Any two data entities with equal values would still compare equal even if they have different metadata.

### Adding Metadata

Metadata can be added to an object using the *with-meta* function by passing it the object and a metadata map. 
The *with-meta* function then returns a new object of the same type with the metadata attached. 

The metadata that can be tagged to an object is always a map that can include other lists, vectors and maps. 

### Equality and Identicalness



