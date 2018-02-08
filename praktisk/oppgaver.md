## Kalender

Start et nytt prosjekt og gi det navnet Kalender \(ny mapppe\).

Lag **kalender.html** - \(! i VSCode\) legg inn link til **kalender.css** \(link:css\) og link til **kalender.js** \(script:src\).

Legg inn følgende innhold i body:

```
        <!-- buttons -->
        <button type="button" class="mybutton" id="prev_year"> &lt; </button>
        <button type="button" class="mybutton" id="next_year"> &gt; </button>
        <button type="button" class="mybutton" id="prev_month"> &lt; </button>
        <button type="button" class="mybutton" id="next_month"> &gt; </button>
        
        <!-- text display -->
        <div class="mytext" id="year">2015</div>        
        <div class="mytext" id="month">oktober</div>
        
        <!-- navn paa ukedager -->
        <div id="ukedager"></div>
        
        <!-- rammen rundt datoer (1..31) -->
        <div id="datoer"></div>
        
        <!-- en liten editor -->
        <div id="tinyed"></div>
        
        <script>
            // start script som tegner calendar
            setup();
        </script>
```

I kalender.css skal du lage regler slik at du får dette utseendet \(bare knappene og overskrift\).  
![](/assets/Skjermbilde 2018-02-08 kl. 13.02.20.png)

```
Grovstruktur på setup() {
   lag ref til elementer i html
   legg til eventlisteners (knappene)
   
   løkke som lager navn på ukedager
   løkke som legger inn 7*6=42 DIVer for datoer
   
   function visKalender(y,m,d) {
     se egen pseudo
   }
   
   // kobla til eventlisteners
   function nextYear(e) { }
   function prevYear(e) { }
   function nextMonth(e) { }
   function prevMonth(e) { }
 } 
```

Lag en enkel `function visKalender(y,m,d) ` som bare oppdaterer årstallet og navnet på måned.

```
pseudokode visKalender(y,m,d)
  la mndNavn = "Jan,Feb,..".split(",")
  lag en ref til årsDiv
  lag en ref til mndDiv
  årsDiv indre html = String(y)
  mndDiv indre html = mndNavn på plass nr m
```

Lag eventlistener for de to øverste knappene slik at vi kan bla fram og tilbake for valgt år.  
Du må ha laga en variabel som lagrer år, måned og dag

```
let activeDate = { y:2018, m:2, d:8 };  // 8 feb 20018
```

Funksjonen som er kobla til de to knappene skal endre **activeDate.y** \( += 1 eller -= 1 \).  
Deretter må de kjøre visKalender\(activeDate.y, activeDate.m, activeDate.d\)

Gjør det samme for de to neste knappene \(de skal endre måned\)

I setup skal du legge til en for løkke som limer inn navn på ukene.  
Hvert navn-på-dag skal lages som en div med klassen **dag**.

Lag en tilsvarende løkke som legger inn 42 div-er som skal vise dato \(1..31\).  
Vi trenger 42 slik at vi har plass til å vise måneder som har den 1st på Søndag.

