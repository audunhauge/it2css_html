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

I utgangspunktet starter videoen på frame 1 og slutter på 256, endre tallene slik at du får med den biten av videoen du ønsker å vise.

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
 ffmpeg -i senterpartiet.mkv -f mp4 sp.mp4
```

\( ffmpeg finnes for linux, osx og windows, har bare testa på linux selv\).

