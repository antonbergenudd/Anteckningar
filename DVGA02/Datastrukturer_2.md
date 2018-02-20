#Datastrukturer 2
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
