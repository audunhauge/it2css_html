# Skjema 

Dersom du ser gjennom tidligere eksamenensoppgaver i IT2 vil du fort merke at
det som oftest er en enkel oppgave i starten (etter en animeringsoppgave) som
går ut på å la brukeren registrere noen data og utføre en enkel beregning.

En typisk løsning er vist under:

```html
<form>
  <br><label> Skriv inn navn <input type="text" placeholder="fornavn etternavn"></label>
  <br><label> Skriv inn alder <input type="number" min=12 max=90></label>
  <br><label> Skriv inn dato <input type="date"></label>
  <br>
  <br><button type="button">Lagre</button>
</form>
```

Dette blir rendra som:

<form>
  <br><label> Skriv inn navn <input type="text" placeholder="fornavn etternavn"></label>
  <br><label> Skriv inn alder <input type="number" min=12 max=90></label>
  <br><label> Skriv inn dato <input type="date"></label>
  <br>
  <br><button type="button">Lagre</button>
</form>
<p>


Merk at her har jeg ikke brukt css for å style, det skal vi undersøke etterhvert.

## Input elementer - basis
Dette er standard input elementer som du må kunne for å løse 
eksamensoppgaver.

1. input text,number,date,color osv
1. input list (med datalist)
1. input checkbox
1. input radio
1. select
1. button

Alle disse bør du ha brukt i løsningen dine slik at du er godt kjent med dem.
Husk at du også kan lese mer om den på devdocs.io (bruk denne slik at du er godt
kjent med den på eksamen).

#### input - skrivefelt

```html
  <input id="fornavn" type="text" placeholder="fornavn">
```
Denne koden lager et input felt som lar brukeren skrive inn tekst.

<input id="fornavn" type="text" placeholder="fornavn">

I js kan du lage en variabel som vist under:
```js
  let inpFornavn = document.getElementById("fornavn");
  let fornavn = inpFornavn.value;
```
Denn koden plukker ut det brukeren skriver og lagrer det i variabelen
 __fornavn__.

Varianter av denne er type="number,email,password"

Andre varianter er "color,date" som har egne visninger (color-picker og calendar)
```html
  <input id="dato" type="date">
```
<input id="dato" type="date" >


#### input list

Denne kombinerer input text med select

```html
  <input id="fornavn" list="land" >
```
<input id="fornavn" list="land" >
<datalist id="land">
 <option value="norge">
 <option value="sverige">
 <option value="danmark">
</datalist>

#### input checkbox

Koden under lager en avkryssningsboks.


```html
  <input id="valg" type="checkbox" >
```
Kryss av for å gi penger <input id="valg" type="checkbox" >

I js kan du lage en variabel som vist under:
```js
  let chkValg = document.getElementById("valg");
  let giPenger = chkValg.checked;
```
Merk at her finner vi ut om boksen er avkryssa med egenskapen checked
som er true/false.