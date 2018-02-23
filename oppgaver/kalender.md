## Kalender

Vi skal lage en kalender som viser en valgt måned \(nokså likt den innebygde komponenten som er kobla til input type="date" \).  
Kalenderen vår skal ha tre visninger: liten - brukes til å vise et helt år, medium - kompakt visning, egna til mobil og maximum - skal dekke hele skjermen - stor tekst \(egna til prosjektor osv\).

#### Prosjekt

Lag en ny mappe \(kalender\), lag ny fil kalender.html i VSCode, skriv ! \(emmet\) og gi dokumentet tittel Kalender.  
Legg inn følgende html

```
    <div id="kalender">
      
        <div class="navigation">
            <button id="prevYear"> &lt; </button>
            <span id="year">2018</span>
            <button id="nextYear"> &gt; </button>
        </div>
        <div class="navigation">
            <button id="prevMonth"> &lt; </button>
            <span id="month">Februar</span>
            <button id="nextMonth"> &gt; </button>
        </div>
        <div id="moonbox">
            <div id="ukedager"></div>
            <div id="datoer"></div>
        </div>
      
    </div>
    <script>
      setup();
    </script>
```

Vi trenger også litt css som ordner layout:

```
#kalender {
    position: relative;
    border: solid green 1px;
    width: 20em;
    height: 15em;
}
#kalender button {
    background-color: lightblue;
    width: 2em;
    height: 1.5em;
    border: solid gray 1px;
    border-radius: 3px;
    box-shadow: 2px 2px 2px gray;
}
#kalender div span {
    padding: 4px;
    padding-left: 10px;
    padding-right: 10px;
}
#kalender div:nth-of-type(2) span {
    width: 4em;
    text-align: center;
}
div.hidden {
    opacity: 0;
}
div.navigation {
    display: flex;
    align-items: center;
    justify-content: center;
}
#datoer,
#ukedager {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
}
div.dato,
#ukedager div {
    width: 35px;
    text-align: center;
}
```

Her bruker vi display:flex til å sentrere navigasjonsknappene og display:grid til å spre ukedager og datoer jevnt utover 7 ruter.

Som vanlig har jeg brukt **setup\(\)** nederst i html-sida - dermed må jeg lage en kalender.js som definerer denne.

Skriv script og velg script:src i head på html sida og lag link til kalender.js.

I kalender.js skal jeg først lage koblinger til elementer som finnes i html:

```
    let spanYear = document.getElementById("year");
    let spanMonth = document.getElementById("month");
    let divUkedager = document.getElementById("ukedager");
    let divDatoer = document.getElementById("datoer");

    let btnNextYear = document.getElementById("nextYear");
    let btnPrevYear = document.getElementById("prevYear");
    let btnNextMonth = document.getElementById("nextMonth");
    let btnPrevMonth = document.getElementById("prevMonth");
```

Jeg trenger noen variable som lagrer aktiv dato \(og en del andre ting\):

```
let minDato = {       // den datoen som skal vises i kalenderen
        year: 2018,
        month: 2,
        day: 1
    };
let  arrDato = [];    // slik at jeg kan traversere datoer senere
```

Jeg trenger også noen funksjoner som kan tegne opp deler av kalenderen for meg:

```
function lagUkedager() {
        let dagNavn = ["Man", "Tirs", "Ons", "Tors", "Fre", "Lør", "Søn"];
        for (let d of dagNavn) {
            let kort = d.substr(0, 2);
            let div = document.createElement('div');
            div.className = "ukedag";
            div.innerHTML = kort;
            divUkedager.appendChild(div);
        }
    }
```

Denne skal lage overskriftene som setter navn på ukedagene. Jeg viser bare de to første bokstavene i dagnavnet.

Jeg trenger en tilsvarende løkke som lager 42 datoer:

```
function lagDatoer() {
        for (let d = 1; d < 43; d++) {
            let div = document.createElement('div');
            arrDato.push(div);                           // <-- NB!
            div.className = "dato";
            div.innerHTML = String(d);
            divDatoer.appendChild(div);
        }
    }
```

Forskjellen på disse to er hovedsaklig at jeg tar vare på en referanse til hver enkel div for datoer.  
**arrDato.push\(div\)**  sørger for at jeg kan traversere alle datoer og endre visning/tekst.  
Jeg trengte ikke ta vare på referanser for navn på ukedagene da disse ikke skal endres etterpå.

Det som mangler nå er en funksjon som kan vise kalender for en valgt måned:

    function visMonth(dato) {
            // trenger å vite hvilken dag 1. av denne måneden er
            let d = new Date(`${dato.year}/${dato.month}/1`);
            let start = (d.getDay() + 6) % 7;
            let mNavn = "Januar,Feb,Mar,Apr,Mai,Jun,Jul,Aug,Sep,Okt,Nov,Des".split(",");
            let mLength = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31];
            spanYear.innerHTML = String(dato.year);
            spanMonth.innerHTML = mNavn[dato.month - 1];
            let lengde = mLength[dato.month - 1];
            for (let i = 0; i < 42; i++) {
                let div = arrDato[i];
                div.className = "dato hidden";  // fjerner gammelt rusk
            }
            for (let i = 0; i < lengde; i++) {
                let div = arrDato[i + start];
                div.innerHTML = String(i + 1);
                div.classList.remove("hidden");
            }
        }

Nå er funksjonene definert, men de er ikke aktivert. Skriv inn nederst i **setup**:

```
 lagUkedager();
 lagDatoer();
 visMonth(minDato);
```

Merk at en funksjon du har definert ikke kjøres automatisk, navnet må invokeres med paranteser bak - slik som setup\(\) i kalender.html - uten invokasjon \(påkalling ved navn\) vil ikke funksjonen kjøres.

