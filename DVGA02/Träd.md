# Träd
###### 12/03/2018

## Introduktion
- Ett träd är en datastruktur som tillåter oss att modellera sådant som vi inte kan modellera med linjära datastrukturer.

- Ett datavetenskapligt träd består av noder med pilar emellan.

- Ett datavetenskapligt träd ritas upp och ner med roten överst.

- Ett träd representerar både en samling noder och någon form av relation mellan dem.


## Matematisk definition av träd

ETt träd är en ändlig mängd T av en eller flera noder (förbundna med riktade kanter) sådant att:

- Exakt en av noderna i T har ingen föregångare. Denna kallas rot
- Resterande noder kan dels in i disjunkta mängder T1, T2,... Tm
- Var och en av mängderna Tm är också ett träd. Dessa mängder Tm Kallas subträd till T. (Ett subträd är kopplat till roten via en riktad kant från roten till suträdets rot)

## Exempel på träd: arvshierkier
- Alla Javas klasser är delar av ett enda träd med Object-klassen som rot.
- Klasserna i Wheels är del av Javas arvshierkier
- Ju  närmare roten en klass ligger desto mer generell blir den.

## Exempel på träd. Komponenhierarki
- Komponenhierarkier kan också modelleras som träd.
- ju närmare roten destor fler komponenter

## Trädterminologi

- Rotnod: Noden utan föregångare
- Riktad kant (edge): Pil som förbinder en nod med en annan.
- Föräldrarnod och barnnod: En nods föregångare kallas föräldrarnod. En nods efterföljare kallas barnnoder.
- Lövnod: En nod utan barn.
- Noddjup: Antalet kanter man måste följa för att komma från roten till noden som söks.
- Höjden på trädet: Det största noddjupet.
- Nodgrad: Antalet barn en nod har.

## Binära träd och binära sökträd

- Binärt träd: Träd vars noder har grad 0,1 eller två. (Maximalt två barnnoder per nod)
- binärt sökträd: binärt träd för vilket gäller för alla noder att datat i vänster subträd är mindre än datat i noden och data i höger subträd är större än det i noden.

## Jämförelse av datastruktur
#### Vilken datastruktur är bäst då vi vill lagra orden i en ordlista eller personer i en telefonkatalog?
- Array
  - Fördel: sökning
  - Nackdel: sätta in, ta bort
- Länkad lista
  - Fördel: sätta in, ta bort
  - Nackdel: sökning
- Binärt ssökträd
  - Fördel: sökning, sätta in, ta bort
  - Nackdel: tar mer data. Idag har vi bra datorer och bortser ofta från detta

## Genomgång av element i ett träd
#### Hur går man igenom dataelement i ett träd på ett systematisk sätt?
- Dataelement i en linjär struktur går man vanligtvis igenom i ordningen från början till slutet
- Med ett träd finns flera möjligheter
- Tre av de mest kända för binära träd bygger på att man går ingeom trädet genom att följa den röda pilen i figuren (se powerpoint för figur)
- På detta sätt kommer alla noder med i genomgången
- Noderna besöks olika natal gånger beorende på hur många barn de har.

#### När ska man titta på värdet i noden?
- Ska man titta på det första gången man kommer till noden och sedan titta på noderna i vänsterträdet och sedan i högerträdet? Kallas __Pre-order__
- Eller ska man titta på värdet i noden efter det att man tittat på vänsterträdets noder? Kallas __In-order__
- Eller, som tredje alternativ, ska man titta på värdet i noden efter det att man tittat i vänsterträdets och högerträdets noder? Kallas __Post-order__

## Praktiska tillämpningar
- Det finns praktiska tillämpningar för de olika sätten att gå igenom noderna i ett binärt sökträd
- Exempelvis kan vi skriva upp aritemtiska uttruck (som 2 * 3) med hjälp av binära träd där sifforna blir lövnoder och * blir rot

- Trädgenomgång i in-order ger infix versionen av det aritemtiska uttrycket: 2 * 3
- Trädgenomg i pre-order ger prefix versionen av det aritemtiska uttrycket: * 2 3
- Trädgenomgång i post-prder ger postfix versionen av det aritemtiska uttrycket 2 3 *

### Infix notation
Det vanligaste notationen för aritmetiska uttryck och den som är mest vanlig i miniräknare
### Postfix notation
Används i vissa miniräknare.
- Man säger att dessa räknare avnäder sig av reverse polish notation efter den polske logikern Lukasiewicz som visade fördelarna med postfix framför infix. Inga paranteser behövs i de aritmetiska uttrycket.
### Prefix notation
I programspråket Lisp används prefix notation för aritmetiska uttryck
- Fördelen med detta skrivsätt blir att de aritmetiska operatorerna, som + och * , får samma syntax som alla andra funktioner.

Exempel där trädet har * som rot barn + och -. + har barnen 2 och 3 och - har barnen 5 och 1.
- Infix: (2+3) * (5-1)
- Prefix: * + 2 3 - 5 1
- Postfix 2 3 + 5 1 - *

### Kommentarer
- Med infix notation krävs ibland paranteser för att få rätt tolkning
- I lisp blir prefix uttrycket (* (+ 2 3 ) (- 5 1))


## Binära sökträd
### Insättning

Antag att vi vill sätta in talen
  - 7, 10, 1, 0, -3. 45. 15. 8
i den ordningen de anges i ett binärt sökträd. Hur går vi till väga?

- Börja med ett tomt träd och lägg till 7 i rotnoden
- Tag sedan 10 och då 10 > 7 sätts 10 in som höger barnnod till 7
- Tag sedan 1, då 1 < 7 sätts 1 in som vänster barnnod till 7
- Tag sedan 0, då 0 < 7 går vi till vänster och då 0 < 1 så blir 0 en vänster barnnod till 1.
- Fortästt på samma sätt med resten av talen


## ADT:n Binärt sökträd

Beskrivning: Skapar ett tomt träd
- BST()

Beskrivning: Kollar om ett element finns i trädet
- search(in: element, ut: boolskt värde)

Beskrivning: Lägger till ett element i trädet
- insert(in: element)

Beskrivning: Tar bort ett element ur trädet
- delete(in: element)

Beskrivning: Kollar om trädet är tomt
- isEmpty(ut: boolskt värde)

Beskrivning: Skriver ut trädet i olika ordning.
- inorder(ut: sträng)
- preorder(ut: sträng)
- postorder(ut: sträng)
