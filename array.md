# Array


Tabeller (array) og strenger (string) kan lagre samlinger av data. En tabell brukes ofte til å lagre lister med like data.
Anta at vi lager en tabell i javascript slik:
```javascript
var elevTabell = [ "Ole","Per","Kari", "Lise","Lars","Oda" ];
```

Da kan du se for deg at tabellen ser slik ut:

| Indeks | Elev |
| -- | -- |
| 0 | Ole |
| 1| Per |
|2|Kari|
|3|Lise|
|4|Lars|
|5|Oda|

Som du ser har hvert element sitt nummer (fra 0). Dette nummeret tilsvarer adressen til verdien.

Med dette bildet i hodet er det lett å forstå hvordan man henter ut en verdi fra en tabell:

```javascript
NavnPåTabell[indeks]
```

Dette betyr: Hent ut verdien fra NavnPåTabell på plass gitt av indeks. 
```javascript
console.log(elevTabell[3]);
// Skriver ut "Lise"
```

Oppdatering/endring av en verdi skjer på samme måte:
```javascript
elevTabell[4] = "Lars Even";```


Legg merke til at all tekst må ha hermetegn rundt seg.
Dersom jeg skrev
```javascript
elevTabell[4] = Lars;

```
da vil js prøve å hente verdien fra en variabel med navnet Lars. Dette vil som oftest gi en feilmelding (fordi variabelen Lars ikke er definert).

## Arbeide med tabeller

Vi har tabellen elevTabell som vi nå ønsker å skrive ut

|Indeks|Elev
|-|-
|0|Ole
|1|Per
|2|Kari
|3|Lise
|4|Lars
|5|Oda

For å skrive ut alle elementene i tabellen bruker vi en løkke:
```javascript
var elevTabell = [ "Ole","Per","Kari","Lise","Lars","Oda" ];
var it;  // løkketelleren
var ant = elevTabell.length;  // antall elementer
for (i = 0; i < ant; i++) {
   console.log(elevTabell[i]);
}```


Her ser vi at alle Tabeller (arrays) har en innebygd egenskap med navnet length som gir deg antall elementer i tabellen.

Denne er viktig å kjenne til slik at du kan finne lengden på tabellen (antall elementer).


## Array funksjoner
|Funksjon|Formål
|-
|push(element)| Legger til ny verdi bakerst i tabellen. Tabellen vokser.
|pop()| Henter ut den bakerste verdien, tabellen krymper.
|shift()| Henter ut den første verdien fra tabellen. De andre verdiene flyttes ned ett hakk. Tabellen krymper.
|unshift(element)| Dytter en ny verdi inn forran i tabellen. De andre verdiene forskyves ett hakk. Tabellen vokser.
|sort()| Sorterer tabellen
|indexOf(element)| Søker etter verdien i tabellen. Dersom den finnes får du indeksen [0..], ellers får du -1.
|join(sep)| Lager en tekst-streng (string) av tabellen. Alle elementene i tabellen blir limt sammen med sep i mellom.
|slice(start,lengde) | [1,2,3].slice(0,2) === [1,2]
|reverse() | [1,2,3].reverse() === [3,2,1]
|Sjekk Array funksjoner på nett for flere|Gjør dette dersom du ønsker toppkarakter.Se på map, slice, each

## Flere dimensjoner
Flerdimensjonale tabeller
Tenk deg at du skal lage et sudoku brett. Brettet er 9 x 9 ruter. 
Du ønsker å bruke en array til å lagre brettet.
```js
var Brett = [
  [ 0,0,0,0,0,0,0,0,0 ],
  [ 0,0,0,0,0,0,0,0,0 ],
  [ 0,0,0,0,0,0,0,0,0 ],
  [ 0,0,0,0,0,0,0,0,0 ],
  [ 0,0,0,0,0,0,0,0,0 ],
  [ 0,0,0,0,0,0,0,0,0 ],
  [ 0,0,0,0,0,0,0,0,0 ],
  [ 0,0,0,0,0,0,0,0,0 ],
  [ 0,0,0,0,0,0,0,0,0 ]
];
```

Merk at det er komma bak alle linjer i tabellen, bortsett fra den siste.
Du kan nå legge inn tallene dine slik:
```js
Brett[0][1] = 4;
Brett[0][2] = 5;
```


Dette kalles en todimensjonal tabell, du må oppgi to verdier 
for å spesifisere en celle i tabellen (tilsvarer (x,y) i koordinatsystemet).
Du kan selvsagt lage tabeller med flere nivåer 
(en tabell inne i en tabell inne i en tabell … …).  
En mye brukt teknikk er å lage en tabell som inneholder objekter .
Et objekt kan for eksempel være informasjon om en elev.
Vi kan da lage en tabell med info om elever slik:
```js
var arrElever = [
  { fornavn:"Ole", etternavn:"Olsen", klasse:"3A", poeng:20 },
  { fornavn:"Lise", etternavn:"Larsen", klasse:"3A", poeng:22 },
  { fornavn:"Lars", etternavn:"Nilsen", klasse:"3B", poeng:21 }
];
```

