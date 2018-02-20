# Kontraktsprogrammering
###### 19-02-2018

### Programmera med kontrakt
Samma som i vardagen, två parter(minst), bägge följer sin del

#### Från ”insidan”

    Vad kräver jag vid anrop av mig
    Vad ger jag tillbaka till anroparen?

#### Från ”utsidan”

    Vad krävs för att anropa modulen?
    Vad får jag tillbaka?


#### Förvillkor och eftervillkor

Förvillkor- vad som ska gälla när metoden anropas, om det inte är uppfyllt är resultat odefinierat.
Eftervillkor - vad som ska gälla när metoden är klar, under förutsättning att förvillkoret är uppfyllt.


#### Varför ska man använda kontrakt?

    Mer strukturerad kod
    Klarare ansvarsfördelning
    Lättare att debugga (hitta testfall)
    Kortare kod
    Mindre redundans(upprepning av samma kontroller)
    Färre fel i färdig produkt (strävar man efter)
