# HTML

HyperTextMarkupLanguage - html er det språket som vi bruker til å beskrive strukturen på ei webside. Vi skal stort sett bruke enkle løsninger i html - det er bare et rammeverk for javascript-koden som vi skal arbeide med.

{% include book.tankhtml %}
Dette eksempelet har med det meste av det vi trenger. Vi bruker alltid denne oppbyggingen av ei webside. 

(html (head ...) (body ... ) (script ... ) )

## HTML-elements
Sjekk [denne](https://developer.mozilla.org/en/docs/Web/HTML/Element) sida for en komplett liste over tilgjengelige elementer.
Vi skal bare sveipe over noen av disse

| Element-navn | Bruksområde | Eksempel
|--|
| h1..h6 | Lage overskrifter | ≺h1≻Stor overskrift≺/h1≻
| p,br | Lage avsnitt, linjeskift | ≺p≻Denne teksten er et avsnitt≺/p≻
| div | Lage en beholder | ≺div≻noe innhold≺/div≻
| span | Lage et tekstområde | Her er ≺span≻noen ord≺/span≻ gruppert
| canvas | Et grafikkområde | ≺canvas id="board" width=100 height=100≻≺/canvas≻
| img | Lage en link til et bilde | ≺img src="demo.jpg"≻
| a  | Lage en link til en adresse | ≺a href="www.vg.no"≻Verdens gang≺/a≻

Dersom vi lager et spill vil vi ofte bruke  
`div/span/canvas`  
da vi ikke har noe [semantisk innhold](https://en.wikipedia.org/wiki/Semantic_HTML) som skal vises.

Dersom vi lager et dokument (med semantisk innhold) vil vi heller bruke elementer som spesifiserer typen av innhold. Dette kommer vi tilbake til når vi skal lage skjema.

Eksempler på *semantic markup* er `article section header footer figure summary`.  
Semantic: ≺summary≻Smittestoffet spres gjennom personkontakt.≺/summary≻  
NonSemantic: ≺div class='summary'≻Smittestoffet spres gjennom personkontakt.≺/div≻






