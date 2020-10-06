## Animeer!

+ Maak de volgende nieuwe functie aan de onderkant van je schets:

``` 
    void animateOneColour(uint32_t c, uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, c);
            strip.show();
        }
    }
```

Zie je dat deze functie **twee** parameters in de ronde haakjes heeft? Later zal je de code van de functie veranderen zodat deze de tweede gebruikt.

+ Verwijder de code in de `loop` functie en voeg een aanroep toe aan je nieuwe functie:

```
    void loop() {
        animateOneColour(strip.Color(0, 0, 255), 100);
    }
```

Merk op hoe je de `animateOneColour` functie twee parameters tussen haakjes doorgeeft? Ook al gebruikt de functie de tweede nog niet, maar de code zal niet compileren als je geen waarden voor alle parameters doorgeeft wanneer je de functie aanroept.

+ Controleer en upload je code. Wat merk je op?

Deze keer hoef je slechts **één regel** code te schrijven die `strip.setPixelColor` oproept, en alle pixels zijn ingeschakeld.

+ Kun je in je nieuwe functie zien dat er nog een paar **accolades** met wat code ertussen zit? Dit paar hoort bij iets dat een **for-lus** \(maar niet de `loop` functie!\) wordt genoemd. Het ziet er zo uit:

``` 
    for(uint16_t i=0; i<strip.numPixels(); i++) {

    }
```

--- collapse ---
---
title: Hoe werkt de code?
---

De bovenstaande code controleert hoeveel NeoPixels in je keten zitten en voert dan de code dat aantal keer binnen de accolades uit.

**Hier is de slimmigheid:** de waarde van `i` begint met `0` en verandert elke keer met `1`, dus telkens wanneer de regel `strip.setPixelColor(i, c);` wordt uitgevoerd, wordt de kleur van de **volgende** pixel ingesteld!

--- /collapse ---

+ Tijd om iets te doen met die tweede parameter! Voeg in je `animateOneColour` functie de volgende regel toe onder de regel `strip.show();`:

```
    delay(wait);
```

Zorg ervoor dat de nieuwe regel **boven** de eerste `}` is, zodat deze in de for-lus zit. Je functie zou er nu zo uit moeten zien:

``` 
    void animateOneColour(uint32_t c, uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, c);
            strip.show();
            delay(wait);
        }
    }
```

In plaats van een bepaald getal te gebruiken voor de `vertraging`, gebruik je de tweede parameter van de functie. Dit betekent dat je een andere waarde kunt kiezen voor de `vertraging` telkens wanneer je de functie oproept.

+ Voeg nog een oproep toe aan je functie binnen `loop` om de NeoPixels zowel uit als aan te zetten:

    ```
        void loop() {
            animateOneColour(strip.Color(0, 0, 255), 100);
            animateOneColour(strip.Color(0, 0, 0), 100);
        }
    ```

+ Controleer je code opnieuw en upload de schets naar de Flora. Nu heb je een coole geanimeerde reeks!

Natuurlijk hoef je de NeoPixels niet uit te schakelen. Hoe zit het om ze allemaal in een stel kleuren een voor een te laten oplichten?

```
    void loop() {
        animateOneColour(strip.Color(255, 127, 0), 100);
        animateOneColour(strip.Color(255, 0, 255), 100);
        animateOneColour(strip.Color(0, 255, 255), 100);
    }
```

+ Voeg zoveel kleuren toe als je wilt. Probeer ook andere waarden dan `100` door te geven voor de tweede parameter, en kijk hoe je animatie versnelt of langzamer wordt!
