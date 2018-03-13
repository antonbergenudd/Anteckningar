# Filhantering
###### 13/03/2018

## Input/Output
Alla program behöver någon form av indata för att kunna påverkas
- Annars skulle programmet göra samma sak varje gång
- Inläsning av text, avläsning av reglage, etc

Alla program behöver ge någon form av utdata för att vara nyttigt
- Utskrift av resultat
- Styrning av motor, etc

Läsning och skrivning i Java består av två delar:
- Input/Output "enheter"
  - System.in System.out, File-object
- Klass som läser/skriver till denna
  - BufferedInputReader, FileInputReader, Scanner

## System.out, System.In
System.out:
- "System.out" motsvarar "standard output". Typiskt sett är detta bildskärmen, textterminalen eller konsol
- Är en "PrintStream" med motsvarande metoder
- Metoden println() skriver en rad avslutat med nyradstecken

System in:
- Motsvarar "standard input", typsikt sett tangetbordet
- Är en "InputStream" med motsvarande metoder
- Metoden read() läser nästa byte från teckenströmmen

Dessa kan omdirigeras när programmet startats Med
- java MinApp <indata> utdata

## Att läsa datat
- Ofta behöver data läsas på annat sätt än per-byte
- Inputstream's har bara byte-reads

- -> Skapa bufferedreader för att läsa en textrad som sträng
      BufferedReader b = new BufferedReader(new InputStreamReader(System.in));
      Sttrin rad =  b.readline();

- -> Skapa en scanner för att läsa ord, tolka siffor etc
      Scanner s = new Scanner(System.in);
      int i = s.nextInt();

## Filhantering
En fil representeras av ett File-object
  - FIle f = new File("fil.txt")
  - Diverse operationer finns
    - f.createNewFile();
    - f.delete();
    - f.exists();
    - f.isFile();
    - f.getName();
    - f.getPath();
    - f.close();

För att skapa en inström:
  - FileInputStream fi = new FileInputStream(f);
  - Kan sedan användas istället för System.in i tidigare exempel

För att skapa en outputström:
  - FileOutputStream fo = new FileOutputStream(f);
  - new PrintWriter(fo).println("Hello");

## Skriv ut innehållet i en fil

      public class PrintFile{
          public void printFile(String filename){
            BufferedReader br ) new BufferedReader( new InputStreamReader(new InputStream (new File(filename))));

            while(String line = br.readLine() != null){
              System.out.println(line);
            }
          }

          public static void main( String [] args){
            printFile app = new printFile();
            app.printFIle(file);
          }
      }
## Filhantering
- Att hantera filer, dvs att läsa eller skriva data till en fil är en viktig del i flesta program.
- Ur javas synvinkel är filer objekt med egenskaper och metoer precis som vilka andra objekt
- Bland en fils egenskaper finns dess namn och dess plats i sekundärminnet.

- I Java finns jlassen File vars objekt sammanlänkar program med fysiska filer. Till File-Klassen finns många metoder (se Java API).

## Läsa från fil
När man läser från tangetbordet skapar man ett Scanner-objekt enligt:
- Scanner scanner = new Scanner(System.in);

System. in är ett objekt som motsvarar tangentbordet.

På samma sätt motsvarar File-objekt filer. När man läser från en fil med filnamn fn skapar man ett Scanner-object enligt nedan:
- Scanner scanner = new Scanner(new File(fn));

Att använda Scanner-objekt till att läsa från filer fungerar ungefär på samma sätt som att använda Scanner-objekt till att läsa från tangentbordet.

Skillnaden mellan att läsa från en fil och från tangentbordet är att:
- filen kanske inte existerar
- filen existerar men finns i fel katalog, dvs fel sökväg
- filen finns i rätt katalog men användaren har skrivit in namnet inkorrekt
- filen finns i rätt katalog och är rätt inskriven av användaren, men användaren har inte rättighet att läsa den.

Dessutom kan man inte kompilera satsen:
- Scanner scanner = new Scanner(new File(fn));

Man får följande felmeddelande:
- Unhandled exception type FileNotFoundException

FileNotFoundException tillhör de undantag som måste tas om hand.
