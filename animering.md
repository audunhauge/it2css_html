# Animering

Nesten all animering vi skal lage i kurset 2inf5 vil være basert på css-animering.
Vi vil hovedsakelig bruke metodene vist under

### keyframes
```css
#tank.moving {
  animation: move_tank 3s;
}

@keyframes movetank {
   0% { left: 20px; }
  100% { left: 500px; }
}
```
Her bruker vi keyframe animation for å flytte en tanks over skjermen.
Tanksen starter på venstre kant og flyttes jevnt utover til 500px fra venstre kant
(px er definert slik at 1px skal være greit synlig som en strek på displayet).

Du kan legge til så mange frames i lista over keyframes som du måtte trenge. I eksemplet har
jeg bare frames for 0% og 100%.

### transition

Denne metoden virker bra for animeringer av endringer (fra rød farge til grønn).
<br>Formen er slik:
```css
 (1)  transition: <property> <duration> <timing-function> <delay>;
```
Et eksempel for tanksen vår som skal kunne rotere.
```css
#tank {
  transition :  transform 1s;
}

#tank.turn_left {
  transform: rotate(15deg);
}
```
Sjekk ut et enkelt eksempel på codepen:

<p data-height="268" data-theme-id="0" data-slug-hash="wGKYqy" data-default-tab="result" data-user="audunhauge" class="codepen">See the Pen <a href="http://codepen.io/audunhauge/pen/wGKYqy/">simpleAnimationExample</a> by audun hauge (<a href="http://codepen.io/audunhauge">@audunhauge</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

Klikk på *Edit on CODEPEN* for å teste ut koden.  
Du kan endre på tallene i `rotasjonen: rotate(90deg)`
eller på tiden som skal brukes  `transition: transform 3s;`

Senere skal vi lage eksempler som tar i bruk alle ledd i transition (1)







