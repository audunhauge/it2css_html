# CSS

Dette kapitlet om css er delt inn i deler som er ment å leses etterhvert som eksemplet tankGame utvides. Du vil bli referert tilbake hit til nye deler etterhvert gjennom resten av boka. Det er *ikke* meningen at du skal prøve å svelge hele dette kapitlet på en gang dersom du er nybegynner i css.

## Bolk-1

Grunnleggende css

### css-regler

En css regel ser slik ut:
```css
   egenskap : verdi ;
```
egenskap er for eksempel bredde, høyde, farge osv

verdi er en gyldig verdi for egenskapen, f.eks 
```css
  width : 100px;
```


### Selectors

For å skrive regler i css må vi skrive en **selector** som sier hvilke elementer i html-dokumentet som skal endres av regelene som er lista opp mellom { }

#### Element selectors

```css
h1 {
  color : white;
}
```

Her er **h1** selectoren, all tekst mellom ≺h1≻ og ≺/h1≻ er det som blir valgt (selected).

**color** er egenskapen til denne teksten som settes til fargen hvit - tekstfargen blir hvit.

Selectors kan velge alle html-elementer slik som

body, h1 h2 .. h6, div, span, p, table tr td .... osv, skrivemåten er som eksemplet over.

#### id selectors

Selectors kan også velge elementer som har en id

html:   ≺div id='brett'≻ dette er en div ≺/div≻

```css
#brett {
  background-color: green;
}
```
Selectoren #brett velger det elementet (det skal være unikt) som har id="brett".
Legg merke til hashtag # foran id-navnet.


#### class selectors

Dersom du har mange elementer som skal ha de samme egenskapene i css, da bør du bruke en class-selector.

html:   ≺div class='funny'≻ dette er en div ≺/div≻≺div class='funny'≻det er dette også ≺/div≻

For å lage en selector for disse to div-ene kan vi skrive

```css
.funny {
  font-size: 1.2em;
}
```

Her har vi en regel som finner alle elementer (div,span ....) som har class='funny' og 
endrer skriftstørrelsen til 1.2em - som gjør den ca 20% større enn den ville vært uten regelen.
