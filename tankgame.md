# TankGame

Dette kapittelet samler alle versjonene av tankGame som
en sammenhengende beskrivelse. De forskjellige delene vil du
også finne spredt rundt i boka der de brukes som eksempler på
stoff som gjennomgås.

Her får du en full oversikt som kan være nyttig dersom du vil
lage prosjektet ferdig uten samtidig å lese hele boka.

### Endringer i game.js

Vi skal legge til noen linjer i game.js
```js
"use strict";

function setup() {
  const MAXSKUDD = 20;        // antall skudd på skjermen
  var poeng = 0;
  
  // to alternative måter som gjør det samme
  console.log(`Vi starter med ${poeng} poeng og ${MAXSKUDD} skudd.`);
  console.log("Vi starter med " + poeng + " poeng og " + MAXSKUDD + " skudd.");
}
```

Som før nevnt tar vi med *use strict* slik at vi får feilmeldinger og andre [gode ting](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Strict_mode).

console.log skriver meldinger ut på konsollet (som du får fram med ctrl+shift+j).
De to metodene for å lime sammen tekst med innhold av variable gir samme resultat.

**Metode-1** bruker et hermetegn som heller mot venstre, slik som \

Det som skjer her er at alle ${ navnPaaVariabel } byttes ut med *innholdet* av denne variabelen. Du kan også utføre beregninger slik som ${antall + 10} eller bare ${2/3}.

**Metode-2** er den klassiske: lim sammen med + (+ kan legge sammen tall eller lime sammen tekst).
Legg merke til at vi må ha hermetegn rundt hver tekst-streng: "Vi starter med ".
Legg merke til at **+** må stå mellom *alle* ledd.

I teoridelen leste du om levetiden og scope for variable. Legg merke til at både MAXSKUDD og poeng er definert inne i funksjonen **setup**. Dermed vil de forsvinne så snart setup er ferdig med jobben sin. Vi kan da bli frista til å flytte dem ut og gjøre dem globale, men heldigvis finnes det en annen løsning. Den vil vi komme tilbake til etterhvert.