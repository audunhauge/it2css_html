# String

Strenger brukes til å lagre tekst. Denne datatypen ligner en del på en tabell (array), men hvert element er en bokstav. Derfor har en variabel av typen String en length egenskap som sier hvor mange tegn som er lagra.
Under vises syntax i javascript for å definere strenger:
```js
var navn = "petter nordsjug";
console.log(navn)   // skriver ut:petter nordsjug
var fornavn, etternavn;
var navnebiter = navn.split(" ");
fornavn = navnebiter[0];
etternavn = navnebiter[1];
console.log("Fornavn:" + fornavn + " Etternavn:"+ etternavn);
// skriver ut Fornavn:petter Etternavn:nordsjug
```

### Flere eksempler
Lime sammen tekst
```js
var fornavn = "Jonas";
var etternavn = "Fjeld";
var navn = fornavn + " " + etternavn;
//Legg merke til at mellomrommet må limes inn eksplisitt,
// ellers blir navnet JonasFjeld.
```

### Splitte tekst
```js
var strMaaneder = "Jan Feb Mar Apr Mai Jun Jul Aug Sep Okt Nov Des";
var arrMaaneder = strMaaneder.split(" ");
Her klippes "Jan Feb .." opp i biter på hvert mellomrom
```

### String-funksjoner
|Funksjon | Forklaring 
|- |- |
|charAt(index:Number = 0):String |Henter ut tegnet på den gitte posisjonen.
|charCodeAt(index:Number = 0):Number|Gir tilbake tallverdien til tegnet på angitt posisjon
|indexOf(val:String, startIndex:Number = 0):int|Leter etter val i strengen, returnerer indeks eller -1 dersom ikke funnet.
|lastIndexOf(val:String, startIndex:Number):int|Leter etter val i strengen fra siste tegn.
|replace(pattern:, repl:Object):String|Bytter ut pattern med repl i strengen (bare den første forekomsten)
|search(pattern:):int|Søker etter pattern og returnerer første hit (-1 hvis ingen match).
|slice(startIndex:Number = 0, endIndex:Number):String|Klipper ut teksten fra start til end-1
|split(delimiter:String):Array|Klipper strengen opp i biter - klipper der hvor delim forekommer.
|substr(startIndex:Number = 0, len:Number):String|Klipper ut en bit fra start og tar len tegn.
|toLowerCase():String|Gjør store bokstaver til små
|toUpperCase():String|Gjør små bokstaver til store


