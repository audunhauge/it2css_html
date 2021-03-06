# Gjentagelser

Ofte vil vi oppdage at vi lager flere kodelinjer som er nesten identiske.
```js
  // kode som skriver ut tallene 1..10 i console
  console.log(1);
  console.log(2);
  console.log(3);
  console.log(4);
  console.log(5);
  console.log(6);
  console.log(7);
  console.log(8);
  console.log(9);
  console.log(10);
```

Dette er tungvint å skrive og vanskelig å vedlikeholde.  
Heldigvis har javascript en struktur som tar seg av gjentagelser.  
Vi skal se på det samme eksempelet laget med en **for** løkke.
```js
var i;
for (i=1; i<11; i+=1) {
  console.log(i);
}  
```

## for-løkke

Denne løkkestrukturen er den vi bruker mest.  
Strukturen er slik:
```js
for (≺startverdi≻; ≺betingelse≻; ≺endring≻) {
  ≺kode som skal gjentas≻;
}  
```
For-løkker trenger vanligvis en løkketeller:
```js
var i;   // løkketelleren
for (i=1; i<11; i+=1) {
  console.log(i);
}  
```
Det er verdiene i denne variabelen som styrer løkka.  
≺startverdi≻ : `i=1`  gir startverdi til løkketelleren  
≺betingelse≻ : `i≺11` så lenge som denne betingelsen er sann skal løkka fortsette.  
≺endring≻ : `i+=1` for hver gang løkka kjøres skal verdien i **i** økes med 1.

### break
Du kan avslutte en løkke før den er ferdig med **break**.
```js
var i;   // løkketelleren
var funnet = false;
for (i=0; i<antallElever; i+=1) {
  if (elev[i].etternavn === finnEtternav) {
    funnet = true;
    break;   // vi har funnet en elev med riktig etternavn
    // og trenger ikke lete lenger
  } 
}  
```
Her brukes *break* til å bryte ut av en løkke som leter gjennom en tabell.


