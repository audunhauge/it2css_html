# Objekter

## Beholder (hash)

En hash er en tabell hvor vi kan slå opp og lagre verdier på en tekst-verdi. I js lager vi en ny hash som et Object.
En hash kalles også for en assosiativ tabell (den assosierer en tekst med en verdi).

```js
var hashByer = { };    // en tom hash (sekk)
// vi skal lagre befolkningen for en del byer
hashByer["Haugesund"] = 28000;
hashByer["Stavanger"] = 180000;

// vi kan lagre på en annen måte
hashByer.Bergen = 250000;
hashByer.Oslo = 550000;

```

For å skrive ut by-tabellen vår bruker vi en spesiell løkke:

```js
var by;
for (by in hashByer) {
  console.log(by + " har " + hashByer[by] + " innbyggere.");
}

```

## Objekt med egenskaper

Variable av typen object er også glimrende til å lagre informasjon som på en eller annen måte *henger sammen*.

Som et eksempel kan vi se for oss at vi skal lagre informasjon om en elev.

```js
var fornavn = "ole";
var etternavn = "olsen";
var adresse = "søllerudveien 36"
var alder = 16;
```

Ulempen er her at hver egenskap eleven har gir opphav til en ny variabel. Her kommer Object til unnsetning:

```js
var elev = {
  fornavn: "ole",
  etternavn: "olsen",
  adresse: "søllerudveien 36",
  alder: 16
}
```
Nå har vi samla all informasjon om eleven inne i *en* variabel.