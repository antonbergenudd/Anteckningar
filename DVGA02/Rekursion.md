# Rekursion
###### 2018-03-06

## Introduktion
### Vad
En rekursiv metod är en metod som anropar sig själv

### Vart
Reukursion används som alternativ till iteration. Det finns programsrpåk som stödjer
- enbart iteration (Fortran)
- enbart rekursion (tidiga verisoner av lisp)
Java stödjer båda

### Varför
Reukursion är en teknik för att lösa problem som innehåller en eller flera problemdelar av liknande sort men som är lättare att lösa.

### För att använda Reukursion krävs
- Ett problem som innehåller ett eller felra delproblem som liknar problmet själv
- Ett enkelt fall av problemet som är lätt att lösa (utan Reukursion). Kallas basfall
- Ett sätt att förenkla problemet så att det kommer närmare basfallet.

### Två roblem som kan lösas med rekursion

- n-fakultet
  - n! = n * (n-1) * (n-2) * ... * 1
- Tornen i hanoi

## Java exempelkod på rekursion vid fakultet
    //Pre: n >= 1
    //Post: result = n!
    public long factorial(int n){
      if( n == 1)
        return 1;
      else
        return n * factorial(n-1);
    }

## Iteration eller Rekursion

- Rekursionen i n-fakultet problemet är en speciell sorts rekursion som kallas svansrekursion (tail Rekursion),
vilket innebär att metoden anropar sig själv enbart en gång och då sist i metoden.

- Att omvandal en svansrekursion till en iteration är lätt, så lätt att till och med kompilatorer kan göra det.
- Andra typer av rekursion kan också omvandlas till iterion, men omvandlingsprocessen och koden är i allmänhet mer komplex
- Den omvända processen att omvandla en iterion till en rekursion går alltid att göra.

### Exempelkod vid beräkning av summa av heltal i en array
- Iterativ metod:

      public int sim(int[] a){
        int summa = 0;
        for (int i=0; i< a.length(); i++){
          summa += a[i];
        }
          return summa;
      }
- Rekursiv metod
      public int sum(int[] a, int startPos){
        if (startPos >= a.length())
          return 0;
        else
          return a[startPos] + sum(a, starPos +1);    
      }
### Exempelkod vid linärsökning
- Iterativ metod:

        public int linearSearch(int[] a, int key){
        int pos = 0;
        while(pos < a.length() && a[pos] != key)
          pos++;
        return (pos < a.length) ? pos : 1;
        }
- Rekursiv metod:

      public int linearSearch(int[] a, int startPos, int key){
        if (startPos >= a.length())
          return 1;
        else if (a[starPos] == key)
          return startpos;
        else
          return linearSearch(a, startpos +1, key);
      }

## Vad ska man använda?
- passar iteration eller rekursion bäst till problemet?
- om rekursion är bäst lämpat är det värt kostnaden i minskad effektivitet?

- Rekursion passar bäst för problem som är naturligt självupprepande som tornen i Hanoi. Koden blir lättare att ksriva och läsa och som en följd av detta lättare att felsöka och underhålla
- Rekursion är långsammare eftersom flera metodanrop är aktiverade samtidigt och systemet måste hantera alla variabler i systemet.

## Rekursiva sorteringsmetoder
### Mergesort
- Denna sorteringsalgoritm är självipprepande och har följande steg.
  - 1) Dela upp listan i två ungefär lika stora listor
  - 2) Sortera rekurvist de två dellistorna, dvs med just denna algoritm
  - 3) Foga samman (merge) de två sorterade dellistorna till en sorterad lista.

### Quicksort
- Detta är den snabbaste sorteringen vi känner till
- Denna sorteringsalgoritm är självupprepande och har följande steg:
  - 1) Välj ett element, kallat pivotlement, ur listan.
  - 2) Ordna om listan så att alla element som är mindre än pivotelementet kommer före detta, och så att alla element som är större än pivotelementet kommer efter detta. pivotelementet har nu fått sin rätta platts
  - 3) Sortera rekurvist de två dellistorna, dvs med just denna algoritm
