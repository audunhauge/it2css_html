# Verktøy

For alle prosjektene i boka er det meningen at du skal lage en egen mappe/katalog.
Vanligvis vil mappa få samme navn som prosjektet, men det er ofte en fordel at navnet er ett ord - slik som **tankGame** eller **tank_game**.

### Nettleser
Jeg velger å bruke nettleseren chrome (allerhelst canary versjonen), men du kan få til omtrent det samme med de fleste moderne nettlesere (NB! *safari* har i de siste årene tatt på seg rollen som Internett Explorer hadde før: den nettleseren som **IKKE** støtter det siste nye).

Muligens det viktigste aspektet med moderne nettlerer er utviklerverktøy.
De er vanligvis tilgjengelige ved å høyre-klikke på en nettside og velge inspect (ctrl+shift+i)

Du kan også få fram console ved å trykke ctrl+shift+j

Console er den plassen hvor du kan teste ut kode, skriv kodebiter og trykk enter for å
se hva som skjer ...

### Editor
Jeg bruker [Microsoft Visual Studio Code](https://code.visualstudio.com/) som har versjoner som virker for Linux, mac og windows.
Andre gode editorer er brackets, textmate, vim, emacs, notepad++ og mange fler.
Jeg valgte code fordi den er gratis, støtter alle os, har god intellisence for js, css og html.

### Git (versjonskontroll)
Dette er et tilleggsverktøy for de som skriver mye kode og som ser nytten av versjonskontroll.
Du trenger ikke dette dersom du bare skriver litt kode knytta til oppgaver i faget, men dersom du setter i gang med egne prosjekt av en viss størrelse - da er dette helt nødvendig.

Skaff deg en konto på [github](https://github.com/) eller [bitbucket](https://bitbucket.org/). Du har en del howtos og dokumentasjon å lese før du kan ta systemet i bruk for å få versjonskontroll på prosjektene dine.

### devDocs
Vanligvis vil vi bruke google til å finne eksempler/documentasjon, men under eksamen/heldagsprøver vil nettet være stengt.
Derfor bør alle installere [devdocs](http://devdocs.io/) og sørge for at javascript, css og html er tilgjengelig offline.

## postgres
Postgres er en god database som er enkel å installere på Mac og Linux.
For mac er den enkleste løsningen å installere [Postgres.app](http://postgresapp.com).

For windows [installer](http://www.postgresql.org/download/windows/)

#### Lag en enkel database
```psql
CREATE DATABASE elevdb;
};
```

#### Lag en tabell i databasen
```psql
create table elev {
   id           INT PRIMARY KEY     NOT NULL,
   fornavn      TEXT    NOT NULL,
   etternavn    TEXT    NOT NULL,
   alder        INT     NOT NULL,
   adresse      CHAR(50)
}

CREATE INDEX etternavn_index ON elev (etternavn);
// søk på etternavn vil nå gå meget raskere.
// spørringer med join på etternavn vil også forbedres meget
```

### Webserver

For testing lokalt er det ofte nødvendig med en webserver, typisk dersom en skal
laste inn filer med data.

#### Enkel python server

På linux og mac kan en åpne et terminalvindu i mappa hvor prosjektet ligger, skriv:
```bash
python -m SimpleHTTPServer
```

Du kan nå koble deg til localhost:8000 og åpne filene i prosjektet.

#### node.js

For linux (ubuntu)
```bash
sudo apt-get install nodejs
sudo apt-get install npm
```

*windows og osx har egne installers*

Du kan nå starte node med kommandoen **node** eller **nodejs**

Skriptet under er en veldig enkel webserver
```js
// Importer http modulen som gjør det meste av arbeidet
var http = require('http');

// Definerer porten vi lytter på
const PORT=8080; 

// en funksjon som tar seg av requests
function handleRequest(request, response){
    response.end('It Works!! Path Hit: ' + request.url);
}

// Lag en server
var server = http.createServer(handleRequest);

// Start serveren
server.listen(PORT, function(){
    // denne funksjonen kjøres når serveren starter
    console.log("Server listening on: http://localhost:%s", PORT);
});
```


