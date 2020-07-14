## Regenbogenspaß

+ Füge am Ende deines Sketch die folgende neue Funktion hinzu. Mach dir keine Sorgen, du musst es jetzt gerade nicht verstehen! Es ist aus dem Beispielsketch ausgeliehen, den du zuvor ausgeführt hast.


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

Mit dieser Funktion kannst du eine beliebige Zahl von `0` bis `255` auswählen und es mischt dir eine Farbe.

+ Füge nun eine weitere neue Funktion hinzu. Überprüfe, ob du die **for-Schleife** darin erkennen kannst!

```
    void lightAllRainbow() {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels())) & 255));
            strip.show();
        }
    }
```

Hier drin steckt  ein bisschen Mathe! Es ist da, um eine schöne Auswahl an Farben gleichmäßig über den gesamten Regenbogen auszuwählen.

+ Du musst nur noch die Funktion aufrufen. Ändere die `loop`-Funktion so, dass nur diese Codezeile enthalten ist. Überprüfe dann dein Sketch und lade ihn hoch, um einen schönen Regenbogen von Farben zu sehen.

```
    void loop() {
        lightAllRainbow();
    }
```

Du musst diesmal keine Parameter verwenden, da die neue Funktion die Farben für dich ermittelt!

+ Wie wäre es mit einer Verzögerung? Schreiben wir eine neue Funktion, die der obigen ähnlich ist, jedoch mit einer zur Schleife hinzugefügten Verzögerung, damit deine NeoPixel animiert werden:

```
    void animateRainbow(uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels())) & 255));
            strip.show();
            delay(wait);
        }
    }
```

+ Ändere den Funktionsaufruf in der `loop`-Funktion und füge eine zweite Codezeile hinzu, um deine andere `animate`-Funktion auch aufzurufen:

```
    void loop() {
        animateRainbow(100);
        animateOneColour(strip.Color(0, 0, 0), 100);
    }
```

Probiere es auf der Flora aus!

--- challenge ---

## Herausforderung: Versuche, deine eigene Sequenzen zu erstellen

+ Versuche, verschiedene Aufrufe der `animateRainbow`-Funktion und deine anderen Funktionen zu kombinieren. Deiner Fantasie sind keine Grenzen gesetzt!

+ Mit den Tricks, die du mit Farben, For-Schleifen und Verzögerungen gelernt hast, kannst du viele coole Dinge tun. Wenn du weitere Beispiele sehen möchtest, lies den Sketch **strandtest**, mit dem du die NeoPixel getestet hast.

--- /challenge ---

--- collapse ---
---
title: Tragbare Stromversorgung
---

Wenn du dein Projekt tragen möchtest, wirst es es wahrscheinlich mit Batteriestrom tragbarer machen wollen.

+ Für die Flora reicht ein 3×AA oder 3×AAA Bateriepack aus. Siehe dazu [dojo.soy/wear2-flora-power](http://dojo.soy/wear2-flora-power){:target="_blank"} für weitere Informationen.

+ Wenn du ein anderes Board verwendest, solltest du den Strombedarf überprüfen.

--- /collapse ---


***
Dieses Projekt wurde von freiwilligen Helfern übersetzt:

Dennis Weber

Lars Reime

Dank freiwilliger Helfer können wir Menschen auf der ganzen Welt die Möglichkeit geben, in ihrer eigenen Sprache zu lernen. Du kannst uns helfen, mehr Menschen zu erreichen, indem Du dich freiwillig zum Übersetzen meldest - weitere Informationen unter [rpf.io/translate](https://rpf.io/translate).
