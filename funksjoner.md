# Funksjoner

En funksjon er en samling av kode inne i et større program som utfører en spesifikk oppgave og er relativt uavhengig av resten av koden.

En funksjon oppfører seg på mye av den samme måten som et vanlig program - men den er ofte kodet slik at den kan brukes flere ganger mens hovedprogrammet kjører.
Funksjoner er viktige verktøy i programmering og kan bidra til å strukturere programmer på en god måte.

Objektorientert programmering går som regel ut på å binde sammen funksjoner og data på en logisk måte, et elev-objekt har funksjoner for å skrive ut elevdata osv.

Mange språk har samlinger av funksjoner i funksjonsbibliotek eller klasser (tenk på Math i actionscript).

Ofte er det nødvendig å sende verdier inn til funksjonene, disse verdiene kalles for parametre eller argumenter til funksjonen.

Et eksempel på dette er sinus funksjonen.
```javascript
var x = 1.2;
var y = sin(x);
```
Her er x en parameter som brukes av funksjonen sin til å beregne en verdi (som lagres i variabelen y).

Mange funksjoner sender tilbake resultatet av en beregning - det gjøres med kommandoen return.
Se eksemplene under for bruk av return.
Dersom du ikke angir noen return verdi, da vil funksjonen returnere verdien undefined. I javascript kan du bare returnere én verdi, men den kan være en av alle definerte typer/klasser.

## Definere funksjoner

Du definerer en funksjon på følgende måte:
```javascript
function navnPaaFunksjon(parameter1, p2) {
   // den neste linja er vanlig
   var r;  // verdien som skal returneres
   // programkode
   // en eller flere linjer, løkker, betingelser osv
   // som oftest gir funksjonen en verdi tilbake
   return r;
}
```
Som et eksempel viser vi definisjonen av sin():

```javascript
function sin(x) {
   var y;  // verdien som skal returneres
   // vi bruker en Taylor approximasjon
   // dette er ikke den reelle definisjonen av Math.sin
   y = x - x*x*x/(3*2) + x*x*x*x*x/(5*4*3*2);
   return y;
}
```


Når funksjonen er definert, kan vi bruke den i kode:
```javascript
var x = 0.7657;
var y = sin(x);
console.log(y);
// skriver ut 0.693..
```
Merk at parantesene etter navnet på funksjonen beskriver hvilke data du skal sende til funksjonen.

Definisjonen: 
```javascript
/**
 * @param {number} x
 * @returns {number} tilnærma verdi for sinus til x
 */
function sin(x) { … }  
```
sier at sin skal ta imot et Number og beregner en ny verdi
av typen Number som returneres.

Denne måten å dokumentere en funksjon på er basert på [jsdoc](http://usejsdoc.org/about-getting-started.html).

## Bruke funksjoner

Dersom du har definert en funksjon selv eller ønsker å bruke en som er ferdig definert i javascript, så er metoden den samme:
```javascript
navnetPaaFunksjonen();
```

Du kjører koden som funksjonen representerer (kroppen til funksjonen) ved å nevne den ved navn - etterfulgt av ().

Dersom funksjonen tar parametre sendes disse i parentesene etter funksjonsnavnet - slik som sinus-funksjonen:

```javascript 
var y = sin(1.23);```

Verdien du sender kan være et tall (slik som over) eller en variabel.
Dersom du bruker en variabel, da hentes verdien ut og sendes til funksjonen -
som om du hadde skrevet det tallet som er lagra i variabelen.
```javascript
var x = 1.23;
var y = sin(x);  // tilsvarer sin(1.23)```

Dette har samme effekt som om du skrev ``` y = sin(1.23)``` siden x inneholder tallet 1.23.

## Avanserte funksjoner

Funksjoner av høyere orden er vanligvis betegnelsen på funksjoner som
tar funksjoner som parameter, eller gir tilbake funksjoner som return-verdi.

Vi skal ikke dykke dypt her, men gi en liten innføring.  
Dette temaet kan du lese mer om på nett dersom du søker på 
*functional programming javascript*.

### Gjennomgang av alle elementer i en array.

Ofte lager vi kode som under for å gå gjennom elementene i en tabell (array).
```js
// anta var elever er en array
for (var i = 0; i < elever.length; i++) {
  // vi gjør noe med elementet elever[i]
  // f.eks vi kjører en funksjon på elementet
  sendBrev(elever[i]);  // sender email til valgt elev
}
```

Det hadde vært nyttig om vi kunne si
```
  ta denne funksjonen (sendBrev) og bruk den på
  alle elementer i elever
```

Vi kan lage en slik funksjon:
```js
function forAlle(arr, handling) {
  for (var i = 0; i < arr.length; i++) {
     handling( arr[i] );
  }
}

// eksempel på bruk
forAlle( elever, sendBrev );
```

### Alle elementer i en tabell skal endres

Tenk deg at du har en tabell som inneholder priser for en webshop.
Nå har det blitt nødvendig å skru opp prisene med 5%.

```js
// anta var priser er en array
for (var i = 0; i < priser.length; i++) {
  priser[i] *= 1.05;   // legger til 5%
}
```

Vi lager en funksjon som kan endre verdiene i en tabell:
```js
function endreAlle(arr, endring) {
  for (var i = 0; i < arr.length; i++) {
     arr[i]  = endring( arr[i] );
  }
}

// eksempel på bruk
function prisVekst(pris) { return pris*1.05; }

endreAlle(priser, prisVekst);
```

## Innebygde array-funksjoner

De to eksemplene vi har vist er allerede ferdiglaga for array i javascript.
```js
  
elever.forEach(sendBrev);
var nyePriser = priser.map(prisVekst);  
// merk at map lager en ny array
// endreAlle funksjonen vi laga over endrer originalen
```

I tillegg finnes 
```js
.reduce .reduceRight .each .filter .every .some
```
som er mer avanserte høyere ordens funksjoner.
Sjekk dem ut på google ... 


{% exercise %}
Lag en funksjon som tar en liste med tall og
gir tilbake en ny liste hvor alle verdiene har øka med 4.
Dvs voks4([1,2,3]) gir tilbake [5,6,7].
Du kan gjerne bruke .map
{% initial %}
function voks4(arr) {
   // din kode her
}
{% solution %}
function voks4(arr) {
  return arr.map(function(e) { return e+4; });
}
{% validation %}
var tall = [1,5,3];
var ny = voks4(tall);
assert(ny[0] === 5);
assert(ny[1] === 9);
{% context %}
{% endexercise %}