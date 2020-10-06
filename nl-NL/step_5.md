## Kleur en licht

Je gaat nu je eigen **functie** schrijven. Functies houden je code netjes.

+ Klik onder aan de schets op **na** de `}` \(dus, buiten de `loop` functie\) en druk een paar keer op <kbd>Enter</kbd>. Typ vervolgens de volgende code:

``` 
    void lightAll() {
        strip.setPixelColor(0, strip.Color(0, 0, 255));
        strip.setPixelColor(1, strip.Color(0, 0, 255));
        strip.setPixelColor(2, strip.Color(0, 0, 255));
        strip.setPixelColor(3, strip.Color(0, 0, 255));
        strip.setPixelColor(4, strip.Color(0, 0, 255));
        strip.setPixelColor(5, strip.Color(0, 0, 255));
        strip.setPixelColor(6, strip.Color(0, 0, 255));
        strip.setPixelColor(7, strip.Color(0, 0, 255));
        strip.show();
    }
```

Opmerking: Alle code in een **functie** staat tussen een paar **accolades** `{ }`.

+ Wijzig nu je `setup` code zodat het er als volgt uitziet:

``` 
    void setup() {
        // put your setup code here, to run once:
        strip.begin();
        strip.show();
        lightAll();
    }
```

De laatste regel code **roept** de functie die je hebt gemaakt aan. Dat betekent dat het de functie laat uitvoeren.

+ Controleer en upload je schets naar de Flora. Zijn alle pixels blauw verlicht?

--- collapse ---
---
title: De pixels tellen
---

Je hebt misschien ontdekt dat het eerste getal in de regel `strip.setPixelColor(0, strip.Color(0, 0, 255));` bepaalt welke pixel moet oplichten.

Heb je gemerkt dat de eerste pixel `0` is in plaats van `1`? Dus als je acht pixels hebt, is de laatste het getal `7`.

--- /collapse ---

+ Wijzig de tweede regel van de `lightAll` functie van:

```
    strip.setPixelColor(1, strip.Color(0, 0, 255));
```

naar:

```
    strip.setPixelColor(1, strip.Color(255, 0, 0));
```

+ Controleer en upload de code naar de Flora. Kun je het verschil zien?

--- collapse ---
---
title: Hoe werken kleuren in code?
---

Op een computer worden kleuren gemaakt door de drie **primaire kleuren** te mengen: **rood**, **groen** en **blauw**.

Je gebruikt getallen van `0` tot `255` om de computer te vertellen hoeveel van elke kleur moet worden gemengd. Dus de code `strip.Color(0, 0, 255)` maakt **blauw** omdat de waarde voor rood en groen beide `0` zijn.

+ Welke kleur denk je dat `strip.Color(0, 255, 0)` je zal geven? Probeer het uit!

--- /collapse ---

Hier zijn nog een paar kleuren die goed zijn om te kennen:

```
    void lightAll() {
        strip.setPixelColor(0, strip.Color(0, 0, 255)); // blauw
        strip.setPixelColor(1, strip.Color(255, 0, 0)); // rood
        strip.setPixelColor(2, strip.Color(0, 255, 0)); // groen
        strip.setPixelColor(3, strip.Color(255, 0, 255)); // magenta
        strip.setPixelColor(4, strip.Color(255, 255, 255)); // wit
        strip.setPixelColor(5, strip.Color(255, 255, 0)); // geel
        strip.setPixelColor(6, strip.Color(0, 255, 255)); // cyaan
        strip.setPixelColor(7, strip.Color(255, 127, 0)); // oranje
        strip.show();
    }
```

+ Probeer te experimenteren met de getallen om verschillende tinten te krijgen. Wat denk je dat je krijgt als je een waarde `0` instelt voor alle drie de kleuren, `strip.Color(0, 0, 0)`?

Zie je al sterren?! Die NeoPixels zijn zeker HELDER, nietwaar!

+ Gelukkig kun je, als je dat wilt, de helderheid aanpassen met de instructie `strip.setBrightness(10);`. Voeg het toe aan de `setup` functie, tussen de regels `strip.begin();` en `strip.show();`. Net als bij kleuren kan het getal alles zijn van `0` tot `255`.

--- collapse ---
---
title: Het aansturen van veel NeoPixels
---

Het kan zijn dat de kleuren aan het einde van de ketting niet goed worden weergegeven. Dit komt omdat het circuit vermogen verliest als gevolg van **weerstand** in de draad.

+ Je kunt dit oplossen door een extra draad te steken langs zowel de **negatieve** als de **positieve** sporen in je circuit.

--- /collapse ---
