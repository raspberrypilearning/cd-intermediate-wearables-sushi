## Knipperende lampjes

+ Maak de volgende nieuwe functie na de eerste:

``` 
    void lightAllOneColour(uint32_t c) {
        strip.setPixelColor(0, c);
        strip.setPixelColor(1, c);
        strip.setPixelColor(2, c);
        strip.setPixelColor(3, c);
        strip.setPixelColor(4, c);
        strip.setPixelColor(5, c);
        strip.setPixelColor(6, c);
        strip.setPixelColor(7, c);
        strip.show();
    }
```

--- collapse ---
---
title: Wat zit er in de ronde haakjes?
---

Deze functie heeft een **parameter**: Dat is het beetje binnen de ronde haakjes. Het is wat extra informatie die je de functie geeft wanneer je die aanroept.

--- /collapse ---

+ Deze keer schrijf je de functieoproepen in `loop` in plaats van in `setup`. Klik in de `loop` functie en voeg code toe zodat het er als volgt uitziet:

```
    void loop() {
        lightAllOneColour(strip.Color(0, 0, 255));
        delay(200);
        lightAllOneColour(strip.Color(0, 0, 0));
        delay(200);
    }
```

--- collapse ---
---
title: Hoe de parameter werkt
---

Zie je hoe je een kleur als **parameter** doorgeeft aan je `lightAllOneColor` functie? Dit is de kleur die wordt gebruikt in plaats van `c` op elke regel binnen die functie. Het betekent dat je dezelfde functie kunt gebruiken om de NeoPixels elke kleur te maken, en je kunt ze zelfs allemaal uitschakelen!

--- /collapse ---

+ Verwijder de regel `lightAll();` vanuit de `setup` functie. Controleer en upload de code.

--- collapse ---
---
title: Over de setup- en loopfuncties
---

Wanneer de Flora wordt ingeschakeld, wordt eerst alle code in de `setup` functie uitgevoerd, en dan wordt de `loop` functie steeds opnieuw uitgevoerd!

--- /collapse ---

+ Wat denk je dat de `delay` (vertraging) functie doet? Probeer verschillende waarden in te voeren voor de **parameter**, bijvoorbeeld `delay(50);` of `delay(1000);`. Vergeet niet om de code te controleren en te uploaden om je wijzigingen te testen!

+ Heb je gemerkt dat de kleur `(0, 0, 0)` de pixels uitschakelt? Probeer de volgende code uit te voeren op de Flora:

```
    void loop() {
        lightAllOneColour(strip.Color(255, 0, 255));
        delay(500);
        lightAllOneColour(strip.Color(0, 0, 0));
        delay(500);
        lightAllOneColour(strip.Color(255, 127, 0));
        delay(500);
        lightAllOneColour(strip.Color(0, 0, 0));
        delay(500);
    }
```

+ Voer nu dezelfde code uit zonder de kleur "uit":

```
    void loop() {
        lightAllOneColour(strip.Color(255, 0, 255));
        delay(500);
        lightAllOneColour(strip.Color(255, 127, 0));
        delay(500);
    }
```

+ Zie je het verschil?

+ Probeer je eigen reeks te ontwerpen door de code in de `loop` functie te veranderen! Je kunt zoveel vertragingen en zoveel aanroepen toevoegen aan je `lightAllOneColor` functie als je wilt. Experimenteer met langere en kortere vertragingen en verschillende waarden voor de kleurparameter.

Vergeet niet dat de hele reeks steeds herhaald zal worden als je de code in de `loop` functie plaatst. 
