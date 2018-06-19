# Datastrukturer 2, del 2
###### 2018-03-05

### Repetition
Kort repetition av ADT:er från föregående föreläsning, se dokumentet Datastrukturer_2

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

## Stackimplementation med lista
- Se powerpoint, Bild 25-26

## Stackimplemntation med array
- Se powerpoint, Bild 27-29

## Stackimplemntation med noder
- Element i stacken lagras som länkade noder.
- Insättning och borttagning görs i början av kedjan av effektivitetsskäl. Den blir då toppen av stacken.
- Vi får skapan en Node-klass för noderna där man kan spara ett stackelement och en "pil"/pekare till nästa nod, dvs en länk till nästa nod.
- För kod, se powerpoint, Bild 31-33

## Syftet med Lab 4 är att:
Ge övning i att:
- använda abstrakta datatyper(ADT)
- använda olika datastruktur
- skriva kommentarer i kod
- göra grafiska gränssnitt
- objektorienterad programmering

## Analys
-Användaren ska kunna lägga till en person i affären
-Användaren ska kunna flytta en av personerna i affären av de två kassaköerna
-Avnändaren ska kunna låta betjäna personen först i någon av kassaköerna
-Dessutom ska det grafiska användargränssnittet hela tiden visa personen (med namn och antal varor) som finns dels ute i butken, dels i de båda kassaköerna

### Analysen ger att vi bör ha klasser för
- Affär
- Kö
- Person

#### Klassen Person
- Namn
- Antal varor
#### Klassen Affär
- Kö
- Lista på personer
- Följande metoder
  - lägga till
  - Flytta
  - Betjäna personen i kön

## Design
- Gör ADT:er. Försök göra ADT:n Kö, gör kontrakt till metoder
- Gör en skiss på layouten och tänk igenom vilka kompontenter som behövs
- Knappar, etiketter, fönster, paneler, textfält
- JList, JList är en klickbar lista som användaren kan klicka på
- När man skapar en JList så används en DefaultListModel i bakgrunden
- Låt listorna i Affär och Kö vara DefaultListModels

## Implementation
- Utgå från klassdiagramet
- Det är bättre att göra många och korta metoder än få och långa
- De tre klasserna för Affär, Kö och Person måste finnas med.
- De tre klasserna ovan måste vara ordentligt dokumenterade i koden med beskrivning och kntrakt för varje metod
- Använda Swing-kompontenten JList för att visa personerna i GUI:t
- Använda datastrukturen DefaultListModel för listorna i Affär och Kö

## Testning
- Testa applikation noga för alla möjliga indata (även de som är "felaktiga"). Tänk på vettiga felutskrifter i GUI:t
- Inga undantag får kastas utan att fångas upp.
