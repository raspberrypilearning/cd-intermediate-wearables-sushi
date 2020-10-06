## Regenboogplezier

+ Voeg de volgende nieuwe functie toe aan het einde van de schets. Maak je geen zorgen, je hoeft het nu niet te begrijpen! Het is ontleend aan de voorbeeldschets die je eerder hebt uitgevoerd.


```
    uint32_t Wheel(byte WheelPos) {
        WheelPos = 255 - WheelPos;
        if(WheelPos < 85) {
            return strip.Color(255 - WheelPos * 3, 0, WheelPos * 3);
        }
        if(WheelPos < 170) {
            WheelPos -= 85;
            return strip.Color(0, WheelPos * 3, 255 - WheelPos * 3);
        }
        WheelPos -= 170;
        return strip.Color(WheelPos * 3, 255 - WheelPos * 3, 0);
    }
```

Met deze functie kun je elk getal kiezen van `0` tot `255`, en een kleur voor je mengen.

+ Voeg nu nog een nieuwe functie toe. Kijk of je de **for-lus** erin kunt zien!

```
    void lightAllRainbow() {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels())) & 255));
            strip.show();
        }
    }
```

Hier zit een beetje wiskunde! Het is er om een mooie selectie van kleuren gelijkmatig uit de hele regenboog te kiezen.

+ Het enige wat over is, is de functie aan te roepen. Wijzig de `loop` functie zodat deze alleen deze regel code bevat. Controleer en upload je schets om een mooie regenboog aan kleuren te zien.

```
    void loop() {
        lightAllRainbow();
    }
```

Je hoeft deze keer geen parameters door te geven, omdat de nieuwe functie de kleuren voor je uitrekent!

+ Hoe zit het met het toevoegen van een vertraging? Laten we een nieuwe functie schrijven die lijkt op de functie hierboven, maar met een vertraging die wordt toegevoegd aan de lus zodat deze je NeoPixels animeert:

```
    void animateRainbow(uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels())) & 255));
            strip.show();
            delay(wait);
        }
    }
```

+ Wijzig de functie-aanroep in de `loop` functie en voeg een tweede regel code toe om ook je andere `animatie` functie aan te roepen:

```
    void loop() {
        animateRainbow(100);
        animateOneColour(strip.Color(0, 0, 0), 100);
    }
```

Probeer het uit op de Flora!

--- challenge ---

## Uitdaging: probeer je eigen reeksen te maken

+ Probeer verschillende aanroepen van de `animateRainbow` functie en je andere functies te combineren. Je fantasie is de limiet!

+ Je kunt veel coole dingen doen met de trucs die je hebt geleerd met kleuren, for-lussen en vertragingen. Als je nog meer voorbeelden wilt zien, bekijk dan de **strandtest** schets die je hebt gebruikt om de NeoPixels te testen.

--- /challenge ---

--- collapse ---
---
title: Draagbare voeding
---

Als je van plan bent om je project te dragen, zul je het waarschijnlijk met behulp van batterijvoeding meer draagbaar willen maken.

+ Voor de Flora is een 3×AA of 3×AAA batterij prima. Zie [dojo.soy/wear2-flora-power](http://dojo.soy/wear2-flora-power){:target="_blank"} voor meer informatie.

+ Als je een ander bord gebruikt, moet je de stroomvereisten controleren.

--- /collapse ---

***

Dit project werd vertaald door vrijwilligers:

Robert-Jan Kempenaar

Sanneke van der Meer

Dankzij vrijwilligers kunnen we mensen over de hele wereld de kans geven om in hun eigen taal te leren. Jij kunt ons helpen meer mensen te bereiken door vrijwillig te starten met vertalen - meer informatie op [rpf.io/translate](https://rpf.io/translate).
