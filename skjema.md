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