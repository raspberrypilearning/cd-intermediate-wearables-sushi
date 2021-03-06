## Wat heb je nodig

### Hardware

+ Adafruit Flora of Gemma
+ Een USB-kabel
+ Ongeveer acht NeoPixels
+ Geleidende draad
+ Drie paar krokodillenklemmen \(je kunt in plaats daarvan ook stukjes geleidende draad gebruiken, maar krokodillenklemmen zijn wellicht gemakkelijker te testen\)
+ Optioneel: Een accu-pack, waarmee je je voltooide project kunt dragen zonder dat het op een computer is aangesloten!

De LED's worden bestuurd door de Adafruit Flora. Je zou ook een Adafruit Gemma, LilyPad Arduino of LilyPad Arduino USB kunnen gebruiken; als je dat doet, zijn er wat kleine codewijzigingen nodig, zoals het nummer van de uitvoerpin en de kaartinstellingen in de Arduino IDE.

Opmerking: De Gemma werkt niet met het Linux besturingssysteem. Het werkt ook niet met een USB 3.0-poort, dus je moet een USB 2.0-poort of -hub hebben om de Gemma op de computer aan te sluiten.

### Software

+ De Arduino IDE

--- collapse ---
---
title: Het installeren en instellen van de Arduino IDE
---

+ Download de Arduino IDE van [dojo.soy/wear2-arduino-ide](http://dojo.soy/wear2-arduino-ide){:target="_blank"} en installeer deze.

+ Open de toepassing zodra deze is geïnstalleerd. Er zijn een paar extra dingen nodig om het voor dit project te laten werken.

+ Open het **Voorkeuren** vanuit het **Arduino** menu. Plak in het vak **Additionele Board Beheer URLs** het volgende en klik op OK.

```
    https://adafruit.github.io/arduino-board-index/package_adafruit_index.json
```

+ Ga in het menu **Hulpmiddelen** naar **Boards** en selecteer **Boards Beheer...**. Kies **Bijgedragen** in het vervolgkeuzemenu. Installeer **Adafruit AVR Boards by Adafruit**. Klik vervolgens op **Sluiten**.

+ Sluit de Arduino IDE af en start deze opnieuw. Ga opnieuw naar het **Boards** menu en je zou de **Adafruit Flora**, **Adafruit Gemma**, **LilyPad Arduino** en **LilyPad Arduino USB** moeten zien. Selecteer het bord dat je gaat gebruiken.

+ Ga in het menu **Schets** naar **Bibliotheek gebruiken** en selecteer **Bibliotheken beheren...**. Typ `neopixel` in het zoekvak. Installeer **Adafruit NeoPixel van Adafruit**. Klik vervolgens op **Sluiten**.

--- /collapse ---

### Aanvullende materialen

+ Een borduurnaald en een schaar
+ Een T-shirt
+ Heldere nagellak
+ Optioneel: Een borduurhoepel (aanbevolen om het stikken van je circuit gemakkelijker te maken)

