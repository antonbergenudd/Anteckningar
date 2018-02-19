ADT-er och datatyper

ADT (abstrakt datatyp)
En programspråksoberoende beskrivning av en mängd
Data
Op. På data
Ex. sant implicerar sant.
Ex. operation: e + e' => e'' plus är operatorn (binär)
"ett heltal plus ett annat heltal ger ett tredje heltal"

Exempel på abstrakta data-typer
-	Mängd
-	Sekvens (lista, kö, stack)
-	Träd (binärt sökträd, AVL-träd, B-träd)
-	graf


Datastruktur
En samling data (sammanbundna), lagringsplats.
När man implementerar en ADT kan man behöva en datastruktur.
En datastruktur kan modellera en abstrakt datatyp

Datastrukturer som modellerar en lista ex.
-	Vector (standard class. Uppbyggt m.h.a. en array)
-	ArrayList (bygger på en array)
-	DefaultList (bygger på Vector)

ADT:n Lista
Datat i en lista utgörs av en ordnad sekvens av ett element.

Klassen Vector
En datastruktur som modellerar en lista.
Det är en typ som kan ta emot andra typer.
Vector finns i paketet java.util

Ex.
Vector <Ellipse> ellipseList
ellipseList = new Vector <Ellipse> ();

//En lista som tar emot ellipser och dubbelkollar så att det är en ellipse.

Array vs. Länkande noder

Länkade noder - en länkad lista ökar lätt dynamiskt
+ effektiv vid insättning
-ineffektiv vid hämtning

Array
+effektiv vid hämtning
-ineffektiv vid insättning och borttagning
Generiska List-klasser vs. List-klasser med Object

test
