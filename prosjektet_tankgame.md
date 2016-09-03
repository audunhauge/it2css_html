# Prosjektet tankGame

Dette prosjektet vil bli brukt som gjennomgående eksempel.
Vi skal utvikle det fra tre tomme filer (game.html game.js game.css)
og vil utvide det med flere filer etterhvert.

Da dette er første gang du møter disse filene, har jeg gitt dem et eget kapittel. Senere vil nye versjoner ligge som underkapitler for
de andre seksjonene (variable, funksjoner ... )

I det følgende bruker jeg *code* som editor, framgangsmåten vil være noe annerledes for andre editorer.

### Første versjon (versjon 0)

#### game.html

Lag en ny mappe med navnet tankGame og start teksteditoren inne i mappa.
I *code* høyre-klikker jeg på sidepanelet og velger new-file.
Jeg skriver inn navnet game.html og nå har jeg en ny html fil som jeg kan skrive kode i.

Første versjon av html filen for tank-game.
{% include book.h1 %}

Den første linja *doctype* er med for at IE skal oppføre seg fornuftig.
Deretter kommer den vanlige strukturen på en web-side
(html (head ) (body   ) )

meta charset=utf8 gir oss fungerende øåæØÆÅ og andre spesialtegn.

De to neste linjene kobler sammen 
```go

.       game.html   (strukturen på websida)
med     game.css    (utseende - farger, plassering osv)
og med  game.js     (kode - hva skal skje, hvordan skal det skje)
```

Jeg har et avsnitt til slutt hvor jeg kjører litt javascript
rett i html filen: setup();

Dette er en standardfunksjon som jeg alltid definerer i hovedfilen for javascript (game.js i eksemplet).
Det er denne funksjonen som starter/klargjør all kode som skal kjøres.


#### game.css

For å lage filen game.css kan jeg i **code** controll+klikke på linken
href="game.css". Jeg kan da velge å lage en ny fil da denne ikke finnes. Andre editorer løser dette på andre måter.

Innholdet av game.css:
```css
#board {
  width: 500px;
  height: 500px;
  background-color: #bfb;  /* lys grønn */
  border: solid red 1px;   /* rød bord */
}
```

Denne css filen sier at elementet med id="board" skal 
ha bredde/høyde på 500px, lys-grøn bakgrunnsfarge og en rød bord (1px bred).  
Farger kan settes på mange måter, hexColor, rgb(), rgba() og fler.

**#board** er her en selector som velger den div-en som har id="board".

Mellom krøllparantesene (curly brakets/braces) kan jeg legge til
så mange css utsagn som jeg måtte ønske. De har alle formen:
```
   egenskap : verdi ;
```
NB! her **MÅ** vi få med semikolon til slutt.


#### game.js

På tilsvarende måte som for game.css ctrl+klikker jeg på linken
src="game.js"

Jeg får da opp en ny tom fil med navnet game.js og skriver inn:
```js
function setup() {
  console.log("We have contact!");
}
```

Dette er definisjonen av funksjonen setup() som jeg kjører helt til slutt i html filen.
Denne første versjonen bruker console.log til å skrive en melding i konsollet.
Du kan se meldingen ved å klikke Ctrl+Shift+J

### Tesing av versjon 0

Sørg for at alle filene er lagret og ligger i samme mappe.
Åpne en ny tab og naviger fram til filen game.html

Du bør nå se en tom side med grønn bakgrunn. Ctrl+Shift+J for å åpne 
konsollet, du bør her kunne se meldingen **We have contact**

Nå har vi et rammeverk som vi kan bruke til utprøving av kode.
Gå i gang med å lese kapitlet om Variable, men ha editoren åpen ved siden av. Bruk også konsollet til å teste kode mens du leser.



