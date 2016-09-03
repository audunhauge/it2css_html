# Kort om språket javascript

Javascript ble laget av Brendan Eich, visstnok på noen få dager.
[En kort oppsummering](https://www.w3.org/community/webed/wiki/A_Short_History_of_JavaScript).
Javascript har lignende syntax som java og c, men [ligner](https://en.wikipedia.org/wiki/JavaScript#Features) mer på lisp/scheme ved at funksjoner er *first class* dvs de kan brukes på samme måte som alle andre objekter i javascript. Dette gjør javascript godt egna til [funksjonell](https://en.wikipedia.org/wiki/Functional_programming) programmering.

# Variable

En variabel er en navngitt beholder som kan inneholde en verdi. Denne verdien kan hentes ut (brukes i en beregning) eller endres/oppdateres.

I javascript må variabelnavn begynne med en bokstav. De kan inneholde bokstaver, tall  _ og $.
Du kan ikke bruke punktum eller mellomrom.

Vanligvis skal en variabel begynne med liten bokstav (stor førstebokstav brukes ofte for klasser). Bruk deskriptive navn, men de bør ikke være for lange (da kan koden bli vanskelig å lese). 
En del variabelnavn er *standard* slik som **i**, **j** og **k** for løkketellere,
**x,y,z** for posisjon i rommet. 
Utenom disse bør du helst ha deskriptive navn, men du kan godt bruke **i** istedenfor løkketeller.
Du bør unngå å havne i java-land hvor de lager variabel/funksjonsnavn som dette:
```java
int numberOfSimilarElementsInTheMainList;
int applicativeResourceAllocatorFactoryFactory() { ... };
void SimpleBeanFactoryAwareAspectInstanceFactory() { ... };
boolean InternalFrameInternalFrameTitlePaneInternalFrameTitlePaneMaximizeButtonWindowNotFocusedState = false;
```

## Variabeldeklarasjoner
I koden din bør du alltid legge til denne linja øverst:

```js
'use strict';
```

Dette er en melding til javascript om at du ønsker feilmeldinger dersom du bruker en variabel uten først å ha deklarert den.

```js
let antall = 0;   // deklarerer en variabel og gir den startverdi
// var antall = 0;   // eldre måte å definere variable på
antal += 1;   // meningen er her å øke verdien lagret i antall med 1
```
Uten use strict vil javascript lage en ny variabel **antal** med verdien undefined [^2]

```js
antal += 1
``` 
vil da gi resultatet NaN (Not a Number).

Med use strict vil du få feilmeldingen

```js 
'antal is not defined' 
```


I eksemplet under lager vi en variabel i javascript:
```js
let i;  // en variabel med navnet "i"
i = 20;     // vi lagrer verdien 20 i variabelen
console.log(i);   // skriver ut 20
i = 5;      // verdien 5 lagres i variabelen
console.log(i);   // skriver ut 5
i = i + 2;  // legg til 2 til verdien i variabelen
console.log(i);   // skriver ut 7
```


Dersom en variabel står på venstre side av et likhetstegn, da tildeles denne variabelen en ny verdi, den nye verdien er resultatet av beregningen på høyre side.

```js
let tall;     // en variabel med navnet "tall"
tall = 20;        // vi lagrer verdien 20 i variabelen
tall = tall + 5;  
// vi beregner tall+5 som er 20+5, verdien 25 lagres i tall
```

Dersom en variabel står på høyre side av et likhetstegn, da hentes verdien ut fra variabelen og brukes i en beregning.


## Variabeldeklarasjon med let
I javascript 2016 er det lagt til en ny måte å definere variable på.

Korfatta versjon: bytt ut **var** med **let**.

#### Forskjeller
```js
function varTest() {
  var x = 1;
  if (true) {
    var x = 2;  // samme variabel!
    console.log(x);  // 2
  }
  console.log(x);  // 2
}

function letTest() {
  let x = 1;
  if (true) {
    let x = 2;  // lager ny variable
                // som bare finnes mellom { }
    console.log(x);  // 2
  }
  console.log(x);  // 1
}

// feilmelding dersom du definerer to variable med samme navn
var a = 12;
var a = 13;  // a = 13
var a = 12;  // a = 12
let b = 12;
let b = 12;  // feilmelding
```

**let** gjør samme jobben som **var**, men uten
de problemene som har vist seg knytta til var.

Grunnen til at de legger til en ny måte å definere variable
på istedenfor å rette på feilene med var, er at så mange
nettsider baserer seg på den eksisterende oppførselen til
var. Derfor har de valgt å legge til **let** slik at
nye script/websider kan bruke denne, mens eksisterende
sider fortsatt virker med den gamle **var**.


## Variabeltyper

I javascript kan du ikke spesifisere at en variabel er av en gitt type, men variablene får type ut fra verdiene som tildeles dem.

Du skal kjenne til og kunne bruke følgende datatyper:

| Type | Eksempel |
| -- |
| String | tekst "Ole" "per" osv |
| Number |Tall, med eller uten desimal, positive og negative|
|Array| Tabell eller liste|
|Object|Hash eller sammensatt datatype basert på en Klasse|
|Boolean|True eller False, Ja/Nei 0/1|

Dermed vil følgende kode
```js
  var tall = 12;
```
lage en variabel med navnet **tall** og typen **Number**.  
Du kan teste dette i consol (ctrl+shift+j), 
skriv inn ```var tall=12;``` og trykk enter.  
Skriv så inn ```tall.``` (tall + punktum)  
Du vil nå se en liste med egenskaper/funksjoner som er kobla til
alle variable av typen Number.  
Lage testvariable av alle typene i tabellen over og se hvordan denne lista (som kommer fram når du skriver punktum bak variabelnavnet) endrer seg.

### Number
Dette er den eneste talltypen som javascript har, andre språk har flere varianter for å lagre tallverdier (heltall, desimaltall ...).  
Start konsollet (ctrl+shift+j) og skriv følgende  
```js
0.2 + 0.1
```
Resultatet på min konsoll ble ```0.30000000000000004```  
Dette viser at Number i javascript har ca 19 gjeldende siffer.
Den forbausende feilen for 0.2 + 0.1 skyldes at tallverdien lagres som et binærtall - da kan ikke 0.3 lagres presist, men som en tilnærmet verdi.

### String
For å lagre en tekstverdi skriver du kode slik
```var s = "heisan";```
Legg merke til hermetegnene rundt teksten. Dersom du ikke har med hermetegn vil js prøve å finne en variabel med navnet *heisan*.

### Boolean
Brukes mye til å lagre resultatet av en test, f.eks vi undersøker om en tanks i et spill har flere skudd igjen :
```js
let flereSkudd = (tanks.skudd > 0);
```
Variabelen flereSkudd vil nå inneholde verdien true eller false.
Dermed kan jeg hente fram resultatet av testen uten å måtte beregne den på nytt.

### Array

Brukes til å lagre mange verdier i en tabell.
Du kan legge inn mange verdier i en array og slå opp på indeks (plassnummer) for å hente ut verdier.

En veldig sentral struktur i all programmering.

### Object

Object er basis-strukturen for det meste i javascript.
Et enkelt eksempel  
```js
let elev = {
  fornavn: "ole",
  etternavn: "olsen",
  adresse: "haugesund"
}
```

## Scope
Scope eller gyldighetsområde avgjør hvor variabelen kan brukes. Levetiden til en variabel bestemmer når den forsvinner (mister sin verdi).
En variabel som er definert inne i en funksjon går ut av scope (forsvinner, mister sin verdi) ved slutten av funksjonen.
```js
setInterval(fly_animasjon, 60);
function fly_animasjon(e) {
  let speed = 0;
  fly.x = fly.x + speed;
  speed += 1;   // vi øker farten for hver frame
}
// denne koden skal akselere et fly over skjermen,
// men flyet blir stående i ro.
```


En variabel som er definert utenfor funksjoner har global scope - dvs de er tilgjengelig overalt.
```javascript
'use strict';
let speed = 0;
setInterval(fly_animasjon, 60);

function fly_animasjon() {
  fly.x = fly.x + speed;
  speed += 1;
}
// denne koden akselerer et fly over skjermen
```

Ulempen med globale variable slik som speed er at det kan være andre bibliotek eller scriptfiler som har definert variable med samme navn.
Du får da kollisjon mellom navnene og programmet er ikke lenger korrekt.
Eksemplet over er ment å illustrere scope (variable har ulik levetid/rekkevidde avhengig av hvor de er definert).
Senere skal vi se på metoder for å unngå bruk av globale variable.

 
## Konstanter
NB! du må ha med *use strict* for å kunne bruke konstanter.
(dette gjalt i 2015).

Konstanter oppfører seg som variable som ikke kan endres etter at verdien er satt. I javascript bruker du ordet **const** istedenfor **var** når du definerer en konstant. Vanligvis vil du definere "magiske" tall som konstanter øverst i koden:
```js
'use strict';
const GRAVITY = 9.8;
const MAX_FIENDER = 20;
```
Dersom du bruker tallet 20 (som er max antall fiender) direkte i koden (sannsynligvis på en god del plasser) og siden finner ut at max fiender bør være 30, da kan du finne at det er ganske vanskelig å få bytta fra 20 til 30 overalt i koden. Noen plasser betyr 20 max-fiender, andre plasser kan tallet 20 være noe helt annet enn antall fiender. Du må sjekk koden rundt tallet for å finne ut om du skal endre til 30 eller la det stå urørt fordi det ikke har noe med fiender å gjøre.

Dersom du bruker const MAXFIENDER kan du ganske enkelt endre tallet der hvor MAXFIENDER er definert - du slipper å søke gjennom koden.

Legg også merke til at konstaner vanligvis defineres med bare store bokstaver.

```js
const GRAVITY = 9.8; 
GRAVITY = 10;         // her får du feilmelding
// du kan ikke endre verdien på en konstant
```

## Kobling mellom variabler og web-sida

For å kunne endre på websida (definert i game.html) må vi lage koblinger
mellom variable i javascript og elementer i html.  
Vi vil vanligvis bruke metoden vist under:
```js
// kobler variabelen divMain til en div med id="main" i html
let divMain = document.getElementById("main");
  
// endrer innholdet som vises på websida
divMain.innerHTML = "ny text som vises på websida";
```


{% include book.t1 %}



### Fotnoter
[^2] Egentlig lager javscript en ny egenskap på windows
objektet med navnet antal.