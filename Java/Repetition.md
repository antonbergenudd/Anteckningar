# Repetition
`06/03/2018`
## Rekursion & iteration
Exempel på problem som kan lösas med rekursion. är "Tornen i Hanoi" & "n-fakultet". Om problemet inte är för komplext, vill man använda rekursion över iteration pga läslighet.

### För att använda rekursion krävs det
* Ett problem som innehåller ett eller felra delproblem som liknar problemet självt.
* Ett enkelt fall av problemet som är lätt att lösa (Basfallet).
* Ett sätt att förenkla problemet så att det kommer närmare basfallet.

# Exempel kod på rekursion / iteration
## N-fakultet

### Rekursiv :+1: :wave: :poop:
    function(n) {
        if n == 1
            return 1;
        else
            return n * function(n-1);
    }

### Iteration :tada:
    function(n) {
        result = 1;
        for(int i = 2; i <= n; i++) {
            result * = i;
        }

        return result;
    }

## Summera tal i vektor

### Iterativ
    int sum(int[] a) {
        int sum = 0;
        for (int i = 0; i < a.length; i++) {
            sum += a[i];
        }
        return sum;
    }

#### Rekursiv
    int sum(int[] a, int startPos) {
        if(startPos >= a.length) {
            return 0;
        } else {
            return a[startPos] + sum(a, startPos + 1);
        }
    }

# Sorterings algoritmer

## Merge sort ( Rekursiv sortering )
1. Delar upp listan i 2 delar
2. Sorterar de två dellistorna rekursivt
3. Foga samman listorna till en sorterad lista

## Quicksort ( Rekursiv sortering )
1. Välj ett referens element ur listan
2. Ordna om listan så att alla element som är mindre än referens elementet kommer före denna, samt alla större hamnar över elementet. Referens elementet har nu fått sin rätta plats.
3. Sortera dellistorna rekursivt, dvs med denna algoritm.

# UML-diagram
## Leguan (klassnamn)
_Klass box för Leguan klassen_

__Egenskaper__
* color: Color
* leftBackLeg, rightBackLeg: Leg
* foodDish: Bowl
* cage: Cage

__Funktioner__
*  +Iguana(aBowl: Bowl, aCage: Cage)
*  +move(): void
*  +eat(): void

(+) public & (-) private

# Objekt relationer

## Beroende
Ett objekt A kan tillfälligt använda ett annat objekt B för att utföra en funktion. De båda objekten är fristående.

## Association
Två objekt A & B som är "jämbördiga" (peer). Båda kan känna till varandra, under en "längre period" ( en referens till objektet lagras som instansvariabel ).

## Aggregat
Ett objekt B tillhör objekt A, när A försvinner, försvinner även B. Om inte B är överlämnad innan dess.

## Komposition
Objekt B är en del av objekt A. När A försvinner, gör B också det ovillkorligen. A & B "kan" inte delas isär ( isåfall är det ett agreggat )

## Arv
B "är" ett objekt A. Skillnad mot föregående relationer: Här är det egentligen bara ett objekt.
