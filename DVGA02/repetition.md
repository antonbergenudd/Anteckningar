# Repetition inför tentan
###### 19/03/2018

1.

  a) Beskriv klassen object
  - Förälder till alla klasser i java, innehåller metoder som alla klasser i Java ska kunna hantera

  b)
  - Public, Alla i programmet kommer åt variabler/metoder
  - Private, Enbart klassen kommer åt variabeler/Metoden
  - Protected, alla subklasser och alla inom samma "paket" kommer åt variabler/Metoder

  c)
  Skillnaden mellan abstrakt klass och gränssnitt
  - Gränssnittet är en namngiven samling funktioner som alla som implementerar interfacet ska kunna hantera.
  - En abstarkt klass är en klass som innehåller en abstarkt klass eller som är definerad som abstarkt, man kan aldrig skapa instanser av en abstarkt klass. För att få "tillgång" till klassen måste man "implementa".

2.
  a)
  - se paint-bild

  b)
  - Klassen AAA och BBB har relationen association

3. Förklara arvspolymorfism:

    - Exemplet nedan visar hur t.ex. både en cykel och ett motorfordon kan adderas till listan Fordon.


      List<Fordon> fordon = new ArrayList<Fordon>();
      fordon.add(new Motorfordon());
      fordon.add(new Cyckel());
