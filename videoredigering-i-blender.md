# Videoredigering i Blender

Start blender og klikk på knappen som vist under og velg Video Editing.

![](/assets/videolayout.png)

Ta tak i høyre hjørne som vist i bildet under og del panelet i to biter:  
\( skråstrekene i høyre hjørne, rett over +\)

![](/assets/splitwindow.png)

Du har nå to like panel oppe til venstre - nederst i det som ligger lengst til venstre skal du klikke på knappen og velge Properties.

![](/assets/prop.png)

Nå skal du ha dette layout på skjermen:

![](/assets/mainview.png)

Nå kan du bruke filbehandleren og dra-slipp filen på området hvor du ser de to stripene \(vises når du slipper filen\).

#### Kommandoer i Blender

* a - velg alle/ingen \(veksler\)
* k - cut/klipp
* g - grab/grip \(flytt med mus - klikk plassering\)
* b - box - tegn en boks rundt elementer du vil velge
* x - erase/xterminate
* Høyre mus - velg

I utgangspunktet starter videoen på frame 1 og slutter på 256, endre tallene slik at du får med den biten av videoen du ønsker å vise. Du kan også **klippe** videoen ved å tykke **k** når du har plassert den grønne streken på ønska frame.  
Klipp ved start og ved stopp, velg de bitene som skal fjernes \(høyre-klikk\) og trykk **x** \(erase\).  
Flytt bitene du skal beholde slik at de ligger ved starten \( velg ved høyre klikk - deretter **g** \(grab\)  og flytt med mus\),  
typisk plassering er frame 1.

Du kan også bruke **b** \(boks select\) og velge lydspor+video samtidig og deretter **g** \(grab\) og klikk for plassering.

Nå kan du høyre-klikke på lydsporet \(det øverste\) - deretter:  i panelet helt til høyre kan du nå krysse av på **Draw waveform** slik at du lett ser hvor det er lyd i klippet.

Mens lydsporet fortsatt er valgt kan du gå inn på Properties \(panel øverst til venstre\) og rulle ned til du ser **Encoding**.

Åpne **Encoding** og rull ned til du ser **Audio Codec ** - denne er i utgangspunktet satt til **None**, skift til **mp3**.

Velg hvor du vil lagre filmen:  **Output** rett over **Encoding** - skriv inn mappe \(f.eks Users/audun/Documents \).  
Velg hvilken type codec du vil bruke \(litt avhengig av hva du har på maskinen - jeg brukte ffmpeg\).  
Størrelsen kan du sette under **Dimensions** : gi X og Y verdier \(bredde, høyde\).  
På samme plass kan du endre start- og slutt-frame.

Velg **Render** - **Render** **Animation** fra menyen \(menylinja for Blender\).  
Vent den tida det tar ... \(det går raskt dersom du velger liten størrelse f.eks 500x500\).

Etterpå kan du bruke ffmpeg til å konvertere til ønska format:

```
 ffmpeg -i senterpartiet.mkv -f mp4 sp.mp4   (på linux)
 /Applications/ffmpeg -i senterpartiet.mkv -f mp4 sp.mp4   (på mac)
```

#### Installering av ffmpeg på mac

Søk opp ffmpeg på nett, last ned versjon som passer for ditt system \(velg disk image for mac\).  
På mac må du flytte ffmpeg inn i Applications mappa \(Programmer\).  
Du må også godkjenne kjøring da den er fra en ukjent \(for apple\) utgiver.

For å bruke programmet på mac må du:

* åpne terminal
* cd til mappa hvor filen ligger  \( cd Documents/mappa/di \)
* kjøre kommandoen:  /Applications/ffmpeg -i  filnavnet.mkv -f mp4 nyttFilnavn.mp4



