# Agents

An *Agent* is a construct that Clojure provides which allows modifications to shared mutable data in the following ways

* asynchronous &
* independent

### Creating Agents

An *agent* can be created with the *agent* function. 

### Mutating the value of an Agent

An *agent* can hold values that can be mutated with *send* and *send-off* functions. 

**send, send-off functions**

These functions accept the following parameters:

* The agent that needs to be updated
* A function, known as an **action**, that would be used to compute the new value of the agent. An **action**

    * is executed on a separate thread
    * is applied at a later point in time
    * should accept one ore more arguments
    * should return a value that becomes the new value of the agent


```clojure
(send the-agent the-function one-or-more-args)
```

which can also be represented as,

```clojure
(send the-agent the-action one-or-more-args)
```


*Inference*

This implies that an agent can be used to run a function (a task) on a separate thread, the return value of which would be the new value of the agent.
These functions are referred to as **actions**.






