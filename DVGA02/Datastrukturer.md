# Datastrukturer DVGA02

## ADT:er och datastrukturer
Begreppen är kopplade till varandra men står för olika saker
ADT (abstrakt datatyp) är abstrakt och är inte kopplade till något programmspråk.
	- Betoning på egenskaper

Datastrukturer är konkreta och till de flesta programmeringsspråk finns en eller flera datastrukturer
	- Betoning på lagringsmetoder

### ADT(Abstrakt datatyp)
En programspråksoberoende beskrivning av en mängd
	- data
	- operationer på denna data

Är abstrakt i den meningen att det inte finns definierat hur datan och operationerna är implementerade (exempel addera ’+’)

Hur värde/värden och operationer precis som primitiva datatyper implementeras med klasser i objekt-orienterade programmeringsspråk.

Exempel på vanliga abstrakta datatyper är:
- mängd
- sekvens (lista, kö, stack)
- träd (binärt sökträd, AVL-träd, B-träd)
- graf

Många programmeringsspråk har inbyggda implementationer av vissa ADT:er

Exempelvis finns olika list-implementationer i Java.

I Java finns också olika gränssnitt för att underlätta implementerandes av ADT:er

### Datastruktur
En datastruktur är en samling data (sammanbundna på något sätt) med ett namn och en mängd operationer-

Operationerna kan variera från datastruktur till datastruktur men inkluderar metoder för att ge till datan.

När man implementerar en ADT kan man behöva en datastruktur.

En datastruktur kan modellera en abstrakt datatyp

I java finns flera datastrukturer som modellerar en lista:
- Vektor   (Bygger på array)
- ArraList (Bygger på en array)
- DefaultListModel (Bygger på en Vector)
- LinkedList (Bygger på länkade noder)


### DT:n Lista
Datat i en lista utgörs av en ordnad sekvens av element.
Operationer utgörs exempelvis av:
- insättning av element (På en godtycklig plats)
- borttagning av element (På en godtycklig plats)
- borttagning av specifikt element
- sökning av element
- beräkning av listans storlek
- kontroll av huruvida listan är tom eller inte
- platsbestämning av ett visst element
- utplockning av element på en viss plats

### Klassen Vector
Klassen Vector är en datastruktur som modellerar en lista

Klassen Vector är en generisk klass, vilket innebär att man med den kan skapa alla typer av listor(exempelvis heltalslistor, ellipslistor, etc).
När man skapar listan (med ’new’) talar man om vad för slags element listan ska innehålla.

Vector <Ellipse> ellipselist = new Vector(Ellipse)();

Klassen Vector finns i paketet java.util.

Vector<E>() Skapar en tom lista av element av typen E
* .addElement( E element) Lägger till ett element av E sist i listan
* .elementAt(int index) Tar bort ett element på positionen index
* .remove(E element) Tar bort första elementet i listan
* .remove(int index) tar bort element på platsen index
* .size() Returnerar storleken på listan



#### Jämförelse Array & Vector samt ArrayList

Arrayer är mer effektiva || en storlek måste anges

Vector & ArrayList är dynamiska, de kan växa och krympa etc || de är mindre effektiva

#### Jämförelse Array & Länkade Listor

Arrayer är effektiva vid hämtning av data || ineffektiva vid insättning och borttagning

Länkade Listor är effektiva vid insättning och borttagning || ineffektiva vid hämtning


### Designmönstret Iterator Pattern
Med Iterator-mönstret kan en klient komma åt innehållet i en datastruktur utan att känna till detaljerna om datastrukturernas uppbyggnad
I java implementeras Iterator-mönstret som gränssnittet Iterator
.hasNext()
.next()
.remove()
