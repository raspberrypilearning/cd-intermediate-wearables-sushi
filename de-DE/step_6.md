## Blinkende Lichter

+ Erstelle nach deiner ersten, die folgende neue Funktion:

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
Titel: Was ist in den runden Klammern?
---

Diese Funktion enthält einen **Parameter**: das ist das Stück in den runden Klammern. Das sind einige zusätzliche Informationen, die du der Funktion gibst, wenn du sie aufrufst.

--- /collapse ---

+ Dieses Mal schreibst du deine Funktionsaufrufe in einem `loop` (Schleife) anstatt im `setup`. Klicke in die `loop`-Funktion und füge einen Code hinzu, so dass es so aussieht:

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
title: Wie der Parameter funktioniert
---

Erkennst du, wie du eine Farbe als **Parameter** zu deiner `lightAllOneColour` Funktion hinzufügen kannst? Dies ist die Farbe, die anstelle von `c` in jeder Zeile innerhalb dieser Funktion verwendet wird. Dies bedeutet, dass du dieselbe Funktion verwenden kannst, um die NeoPixel in einer beliebigen Farbe zu gestalten, und du kannst sie sogar alle ausschalten!

--- /collapse ---

+ Lösche die Zeile `lightAll();` aus der `setup`-Funktion. Überprüfe den Code und lade ihn hoch.

--- collapse ---
---
title: Über die Setup- und Loop-Funktionen
---

Wenn die Flora eingeschaltet wird, wird der gesamte Code in der `setup`-Funktion zuerst und dann die `loop`-Funktion immer und immer wieder ausgeführt!

--- /collapse ---

+ Was denkst du, tut die `delay` (Verzögerungs) -Funktion? Versuche, verschiedene Werte für den **Parameter** einzugeben, zum Beispiel `delay(50);` oder `delay(1000);`. Vergesse nicht, den Code zu überprüfen und hochzuladen, um deine Änderungen zu testen!

+ Hast du bemerkt, dass die Farbe `(0, 0, 0)` die Pixel ausschaltet? Versuche, den folgenden Code auf der Flora auszuführen:

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

+ Führe jetzt denselben Code ohne die Farbe "Aus" aus:

```
    void loop() {
        lightAllOneColour(strip.Color(255, 0, 255));
        delay(500);
        lightAllOneColour(strip.Color(255, 127, 0));
        delay(500);
    }
```

+ Erkennst du den Unterschied?

+ Versuche, deine eigene Sequenz zu entwerfen, indem du den Code in der `loop`-Funktion änderst! Du kannst deiner `lightAllOneColour` Funktion so viele Verzögerungen und Aufrufe hinzufügen, wie du möchtest. Experimentiere mit längeren und kürzeren Verzögerungen und unterschiedlichen Werten für den Farbparameter.

Denke daran, dass sich die gesamte Sequenz immer wieder wiederholt, wenn du deinen Code in die `loop`-Funktion einfügst. 
