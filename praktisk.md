# Praktiske eksempler

## Variabeldeklarasjoner
```js
var tall = 12;
var navn = "ole";
var elev = { fornavn:"ole", etternavn:"olsen" };
var ferdig = false;
var tabell = [ 1,2,3 ];
```
## Beregninger
```js
var verdi = (12 + 3) / 4;
var vinkel = Math.asin(3/4);
var minst = Math.min(verdi, vinkel);
```

## Betingelser og valg
#### enkel if
```js
// enkel if
if ( betingelse ) {
	// handling dersom sann
} else {
	// handling dersom usann
}
```

#### if else if
```js
if ( betingelse1 ) {
	// handling dersom betingelse1
} else if ( betingelse2 ) {
	// handling dersom betingelse2
}
// kan gjentas med så mange betingelser som nødvendig

```

## Løkker

#### for løkke

```js
var i;
for (i=0; i < 10; i++) {
	// kode som gjentas 10 ganger
}

// ECMA6
for (let i=0; i < 10; i++) {
	// kode som gjentas 10 ganger
}

```

#### while løkke
```js
var i = 0;
while (i<10) {
	// kode som gjentas 10 ganger
	i++;
}
```

#### travasering av array

```js
// vi antar at tabell er en array
var i;
var antall = tabell.length;
for (i=0; i < antall; i++) {
	var verdi = tabell[i];
	// kode som gjør noe med hver verdi
}
```

#### finn minste / største verdi i en array
```js
// vi antar at tabell er en array av tall
// f.eks tabell = [1,2,3-5,8,0,1222]
var minst = Math.min.apply(null,tabell);
var storst = Math.max.apply(null,tabell);
```


## lese en fil
NB! Denne metoden virker bare dersom du laster sida fra en webserver.

I eksemplene under antar vi at funksjonen ** behandle ** tar seg
av bearbeiding av motatt data.

#### bruk av fetch
Koden under bruker fetch metoden som støttes av moderne nettlesere slik som
Chrome og Firefox.

```js
var url = "elevliste.json";
fetch(url).then(r => r.json())
  .then(data => behandle(data))
  .catch(e => console.log("Dette virka ikke."))
```

#### bruk av xhr
Denne metoden virker i alle nettlesere, også de som er gått ut på dato.
```js
var url = "elevliste.json";
var xhr = new XMLHttpRequest();
xhr.open('GET', url);
xhr.responseType = 'json';

xhr.onload = function() {
  behandle(xhr.response);
};

xhr.onerror = function() {
  console.log("Dette gikk ikke bra.");
};

xhr.send();
```
