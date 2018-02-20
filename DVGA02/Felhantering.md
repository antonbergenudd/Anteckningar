# Felhantering
###### 19-02-2018/20-02-2018

### När det går fel
När vi använder Input/Output från/till användaren kan saker och ting gå fel som är utanför programmerarns kontroll.
Exempel:

* Fel typ av indata
* Filen man försöker öppna finns inte
* Användaren har inte rättigheter att öppna eller skriva till en viss fil

I java skapar systemet ett undantag(exception) som är ett objekt som innehåller information om felet eller den ovanliga situation som inträffat då programmet körs.

Precis som vi kan ta hand om andra event kan vi ta hand om undantag, dvs vi kan skriva undantagshanterare (exception handels) för att ta hand om problem.

### Undantag

I exemplet angav användaren fel typ av indata

Detta fel kan vi förutsäga även om felet kanske inte händer så ofta. För förutsägbara problem kan använda en if-sats för att testa om ett problem inträffat

Alternativet är att använda en try - catch istället för en if-sats

##### Tre viktiga subträd till Throwable:

* Error: Motsvara problem som vi varken kan undvika eller lösa.
* Exception: kompilatorn kontrollerar om vi implementerar hanterare för dessa undantag
* RuntimeException: Kompilatorn tvingar oss inte att ha hanterar för dessa undantag.

##### Metod för säker inmatning av heltal:

    public int secureInt(){
    int number = 0;
    boolean count = true;
    Scanner scanner ) new Scanner(System.in);

    while(count){
      try{
        number = scanner.nextInt();
        count = false;
      }catch ( InputMismatchexpection e){
        Scanner.nexLine();
        system,out.println(number + "is not a number number, try again");
      }
    }
    return number;
    }

#### Exempel på flera catch satser till en try
    try{
      //Java-satser som kan kasta undantag
    }catch(...){
      //Första undantaget
    }catch(...){
      //Andra untantaget
    }catch(...){
      //Tredje undantaget
    }

#### Hur kastar man undantag?

##### Med If-sats och error:

    public int division(int taljare, int namnare)
    {
        int kvot = 0;
        if (namnare == 0){
          System.err.println("Nämnare kan inte vara 0.");
          System.exit(1);
        }
        else
          kvot = taljare/namnare;
        return kvot;
    }

##### Med If-sats och throw:

    public int division(int taljare, int namnare){

      int kvot = 0;
      if(namnare == 0)
      {
        throw new IllegalArgumentExpection("Nämnaren kan inte vara 0.")
      }
      else
        kvot = taljare/namnare;
      return kvot;
    }

##### Med Kontrakts Programmering:

    //pre: namnare !=0
    //Post kvot = taljare och namnare

    public int division(int taljare, int namnare){
      int kvot = taljare/namnare;
      return kvot;
    }
