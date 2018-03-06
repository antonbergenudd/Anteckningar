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
      else return n * factorial(n-1);

    }
