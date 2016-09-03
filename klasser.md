# Klasser

Jeg velger å beskrive klasser ut fra siste versjon som er implementert i 
nettleseren Chrome (mars 2016).  
Den eldre løsningen for klasser vises i et tillegskapittel.

## Class

```js
class Rektangel {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
};

var r1 = new Rektangel(30,40);
```
Her har jeg definert en ny klasse med navnet Rektangel.
Merk at jeg må definere klassen før jeg bruker den, klasser blir
ikke *hoisted* (flyttet til toppen av scopet) slik som funksjoner.

En klasse kan bare ha en funksjon med navnet **constructor**.
Det er denne funksjonen som kjøres når du
lager en ny instans (en variabel av klassen, slik som r1 er en 
instans av klassen Rektangle).

Dersom du tester koden over i consol (ctrl+shift+j)
(copy paste koden inn i consol, trykk deretter enter)
og så skriver **r1** og trykker enter, da viser chrome:  
```js 
Rektangel {height: 30, width: 40}
```
Dette sier oss at variabelen *r1* er av typen *Rektangel*
og har innhold `{height: 30, width: 40}`.  


## Eksempel - definisjon av en klasse for elev

```js
class Elev {
  constructor(id, fn, en, klasse) {
    this.fornavn = fn;
    this.etternavn = en;
    this.klasse = klasse;
  }
}

var elev = new Elev(123,"petter","olsen","3a");
elev.fornavn === "petter";  // true
elev.klasse === "3a";  // true

// Lagre data for mange elever
var elever = [ ];

elev = new Elev( ....);
elever.push(elev);
...  // repetert mange ganger
```


## Eksempel - definisjon av klassen Tank

Denne klassen skal vi bruke i spillet vi lager.

```js
const MAXSPEED = 23;
const TURN = 3;
const FIREWAIT = 6;
const AKS = 2;

class Tank {
  constructor(id, x, y, color) {
    this.id = id;
    this.color = color;
    this.alive = true;
    this.magazin = 20;
    this.maxhealth = 100;
    this.hitpoints = 100;
    this.speed = MAXSPEED;
    this.turnrate = TURN;     // hvor mange grader/tidsenhet kan tanken rotere
    this.v = 0;               // fart
    this.a = AKS              // akselerasjon
    this.x = x;               // plassering på skjermen
    this.y = y;         
    this.w = 20;              // bredde
    this.h = 32;              // høyde
    this.rot = 0;             // rotasjon - retning tanken peker
    this.firewait = FIREWAIT;
    this.fired = 0;           // cooldown for fire-rate
    this.div = document.createElement('div');
    this.div.classList.add('tank');
    this.div.classList.add(color);
  }
  
  // slik at vi kan spørre if (obj.is("tank"))
  // alle kolliderbare ting i spillet kan svare på dette spørsmålet
  is(t) { return t === 'tank'};
  
  // påfør denne tanken skade, den blir treigere
  // merk at hitpoints endres ikke her
  hurt() {
    this.firewait += 2;
    this.turnrate *= 0.9;
    this.speed *= 0.9
  }
}

// Nå bruker vi klassen til å lage en ny tanks 
// og legger den ut på spillebrettet
var t = new Tank("t1",10,10,"red");
document.getElementById("game").appendChild(t.div);
```

