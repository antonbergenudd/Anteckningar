# Datastrukturer 2, del 2
###### 2018-03-05

## Repetition på föregående föreläsning, se Datastrukturer_2

### We want to separate what an abstraction is from how it is implemented

- Implementations of the same abstraction can be substituted freely

### The implementation of a data object is concerned with how that object is represented in the memory of a computer

- This information is called the representation, or rep for short

### We need a way of changing the representation without having to change all client programs.

 - Allows changing implementations without affecting clients.
 - Encapsulate the rep with a set of operations
 - Restrict clients so that they cannot manipulate the rep
    - Clients must call the operations
    - information hiding, ex private variables. Getters and setters is used instead

## Implementation of a Data Abstraction
### To implement or re-implement the data abstraction
- Define the rep
- Implement the operations in terms of it

### Client code is not affected by a change
- Neither in the rep(the data structure) nor in the code (algorithms)

## Benefits of Data Abstractions: Locality

### The implementer of an abstraction know what is needed
- Described in the specification
- No interactions or only limited interacting are needed with programmers of other modules

### The implementer of a client module knows what ot expect
- Namely the behavior described by the specification

### The program can be studied one module at a time
- Specifications are much smaller than implementations
- Determine wha tit does and whether it does the right thing
- Ignore both client modules, and modules that it uses
### Program modification can be done module by module
- Improve performance, correct an error, provide extended facilities without affecting other modules


##  Abstract Data Type: Algebraic Specification &&  Abstract Data Type: Functions && Transition to Abstracts Class
- Se powerpoint för beskrivning av hur en Stack ADT och dess funktioner beskrivs formelt.
