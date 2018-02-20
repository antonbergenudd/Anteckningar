# Datastrukturer 2
###### 20-02-2018

### ADT:n Mängd (På engelska kallas det bland annat Bag)

* En oordnad samling av unika element.
* Kan innehålla ett obegränsat antal element.
* Exempel på operationer
* Skapa en tom mängd
* Kolla om ett element finns i mängden
* Lägg till ett element i mängaden. Observera att dubletter ej får förekomma i mängden
* Ta bort ett element ur mängden. Observera att elementet måste finnas i mängden för att man ska kunna ta bort det
* Kolla om mängden är tom eller inte
* Kolla hur mpnga element som finns i mängden


Exempel på egenskaper
- En oordnad samling av unika element
-  Kan innehålla ett obegränsat antal element
##### Tom mängd
    Beskrivning: Skapar en tom mängd.
    Pre: Sant.
    Post: en ny tom mängd har skapats
    Mängd()
##### Kollar om ett element finns
    beskrivning: Kollar om ett element finns i mängden.
    Pre: Sant.
    Post: resulatat = sant om elementet finns i mängden, annars falsk.
    containts(in: elements, ut: boolskt värde)

##### Lägger till ett element
    Beskrivning: lägger till ett element i mängden.
    Pre: !Conaints(element)
    Post: Element är lagt till mängden.
    add(in: element)
##### Tar bort ett element

    Beskrivning: Tar bort ett element ur mängden.
    Pre: conaints(element)
    Post: elementet är borttaget ur mängden
    remove(in: element)
##### Kollar om mängden är tom
    Beskrivning: Kollar om mängden är tom.
    Pre: sant
    Post: resultat = sant om mängden är tom, annars falskt
    isEmpty(ut: boolskt värde)
##### Bestämmer mängdens storlekt
    Beskrivning: Bestämmer mängdens storlek
    Pre: sant
    Post: resultat = mängdens storlek
    size(ut: heltal)

#### Gränssnitt

De operationer som finns till en ADT kan samlas i ett gränssnitt som en implementering av ADT:n kan implementera.

Exempel på Javagränssnitt för ADT:n Mängd

I Paktetet java.util finns gränssnittet:

    public interface SetADT<E>{
    public boolean contains(E element);
    public void add(E element);
    public void remove(E element);
    public void isEmpty();
    }

#### ADT:n Lista

##### Exempel på egenskaper:
* En ordnad sekvens av element.
* Kan innehålla et obegränast antal element

##### Exempel på operationer:
* Skapa en tom Lista
* Kolla om ett element finns i listan
* Lägg till ett element op en viss plats i listan.
* Ta bort element på en viss plats i listan.
* Kolla om listan är tom eller inte.
* Kolla hur många element som finns i listan

#### ADT:n Beskriven med kontrakt

##### Tom lista
    Beskrivning: skapar en tom lista
    Pre: Sant
    Pos: en ny tom list har skapats.
    Lista()
##### Kollar om ett element finns
    Beskrivning: Kollar om ett element finns i lista
    Pre: Sant
    Post: resultat = sant om elementet finns i listan, annars falskt
    contains(in: element, ut: boolskt värde)
##### Lägga till element
    Beskrivning: Lägger till ett element på ett visst index i listan.
    Pre: 0 <= index <= size()
    Post: element har lagts till på platsen index
    add(in: element, index (heltal))
##### Ta bort element
    Beskrivning: Tar bort ett element på ett visst index ur listan.
    Pre: 0 <= index < Size()
    Post: element på platsen index har tagits bort ur listan
    remove(in: index(heltal))
##### Kollar om listan är tom
    Beskrivning: Kollar om listan är tom
    Pre: Sant
    Post: resultat = sant om listan är tom, annars falskt
    isEmpty(ut: boolskt värde)
##### Bestäm listans storlek
    Beskrivning: Bestämmer listans storlek
    Pre: Sant
    Post: reusltat = listans storlek.
    Size(ut: heltal)

#### ADT:n Kö
##### Exempel på egenskaper:
* En ordnad sekvens
* Kan innehålla ett obegränast antal element
* FIFO (First in First out)

##### Exempel på operationer
* Skapa en tom kö
* Lägg till ett element sista i kön
* Ta bort element först i kön och ta hand om det.
* Kolla om kön är tom eller inte

#### ADT:n Beskriven med kontrakt

##### Skapa en kö
    Beskrivning: Skapar en tom kö
    Pre: sant
    Post: en ny om kö har skapats
    Kö();
##### Lägg till element
    Beskrivning: Lägger till ett element i kön
    Pre: sant
    Post: element är tillagt sist i kön
    enqueue(in:element)
##### Ta bort element
    Beskrivning: Tar bort elementet först i kön och skickar tillbaka det.
    Pre: !isEmpty()
    Post: elemetet först i kön är borttaget och returnerat
    dequeue(ut: element)
##### Kolla om kön är tom
    Beksrivning: Kollar om kön är tom
    Pre: sant
    Post: resultat = sant om kön är tom, annars falskt
    isEmpty(ut: boolskt värde)

#### ADT:n Stack
##### Exempel på egenskaper
* En ordnad sekvens av element
* Kan innehålla ett obegränast antal element
* LIFO (Last in First out)

##### Exempel på operationer
* Skapa en tom stack
* Lägg till element överst på stacken
* Ta bort elementet överst på stacken och ta hand om det
* KOlla om stacken är tom eller inte

#### ADT:n Beskriven med kontrakt
#####  Skapar en tom stack
    Beskrivning: Skapar en tom stack
    Pre: sant
    Post: en ny tom stack skaps
    Stack()
##### Lägg till ett element
    Beskrivning: Lägger till ett element på stacken
    Pre: sant
    Post: elementet är lagt överst på stacken
    push(in: element)
##### Ta bort ett element
    Beskrivning: Tar bort elementet överst på stacken.
    Pre: !isEmpty()
    Post: elementet överst på stacken är borttaget och returnerat
    pop(ut: element)
##### Kolla om stacken är tom
    Beksrivning: Kollar om stacken är tom
    Pre: sant
    Post: resultat = sant om stacken är tom, annars falskt
    isEmpty(ut: boolskt värde)  

### Implementationer av ADT:er

En ADT kan impementeras på en många olika sätt.

Bur man implemeterar en ADT spelar inte någon större roll så länge man får med de egenskaper och operationer som agetts i ADT:n

Exempelvis kan ADT:n Stack implementeras med hjälp av:
* lista
* array
* noder

#### Stackimplementation med Lista
* En javaListKlass (DefaultListmodel) används för att spara element i stacken.
* Defailt List mode kan användas tillsammasn med Jlist för att visa element i ett GUI.
* Toppen på stacken har valts till index 0.

För kod se föreläsning 12, datastrukturer 2. Sida 17.
