# Hjelpebiliotek

For å gjøre kodingen vår litt enklere bruker vi et lite bibliotek
som inneholder mye brukte funksjoner.

Slike bibliotek bruker ofte en bokstav/tegn som utgangspunkt for å kjøre alle
funksjoner fra, jQuery bruker $, underscore bruker _.

For å ikke skape forvirring velger jeg **zz** som navn på biblioteket
og gjemmer alle funksjoner inne i det navnet.

Du kan selvsagt kalle biblioteket ditt for **mittBibliotek**, men poenget
er at vi ønsker at mye brukte fraser skal bli korte.  
Dermed zz("brett") framfor mittBibliotek("brett").


```js
  // Kode uten bruk av biblioteket:
  let divBrett = document.getElementById("brett");
  
  // Kode med bibliotek
  let divBrett = zz.$("brett");
```
Dette er nyttig da slike oppslag i DOM (Document Object Model) forekommer
hyppig i web-apper.

## Bibliotek-koden

```js

class ZZ {

    addClass(selector, klass) {
        let elm = [...document.querySelectorAll(selector)];
        elm.forEach(e => e.classList.add(klass));
    }

    removeClass(selector, klass) {
        let elm = [...document.querySelectorAll(selector)];
        elm.forEach(e => e.classList.remove(klass));
    }

    // finner et element, kan bruke "#brett", "brett", ".klasse"
    // for nakne ord $("main") brukes getElementById
    // ellers $("#main") vil bruke querySelector
    $(selector) {
        // fails for div span etc
        if (selector.includes("#") || selector.includes(".") ) {
            return document.querySelector(selector);
        } else {
            return document.getElementById(selector);
        }
    }
}

let zz = new ZZ();
zz.all = document.querySelectorAll.bind(document);
// nå er zz.all et synonym for document.querySelectorAll

```

## Codepen

En demo i codepen som viser tre forskjellige måter du kan bruke
zz.$(  ) funksjonen på. Klikk på JS knappen for å se koden som kjøres.

<p data-height="268" data-theme-id="0" data-slug-hash="reMrwP" data-default-tab="result" data-user="audunhauge" class="codepen">See the Pen <a href="http://codepen.io/audunhauge/pen/reMrwP/">jQueryMINI</a> by audun hauge (<a href="http://codepen.io/audunhauge">@audunhauge</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>
