## Animieren!

+ Erstelle die folgende neue Funktion im unteren Teil deines Sketch:

``` 
    void animateOneColour(uint32_t c, uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, c);
            strip.show();
        }
    }
```

Kannst du sehen, dass diese Funktion **zwei** Parameter in den runden Klammern benötigt? Später ändere den Code der Funktion so, dass nur zweite verwendet wird.

+ Lösche den Code in der `loop` -Funktion und füge einen Aufruf zu deiner neuen Funktion hinzu:

```
    void loop() {
        animateOneColour(strip.Color(0, 0, 255), 100);
    }
```

Bemerkst du, wie du zur `animateOneColour` -Funktion zwei Parameter in den Klammern hinzufügst? Obwohl die Funktion die zweite noch nicht verwendet, wird der Code nicht kompiliert, wenn du beim Aufrufen der Funktion nicht für alle Parameter Werte eingegeben hast.

+ Überprüfe deinen Code und lade ihn hoch. Was fällt dir auf?

Diesmal musste nur **eine Zeile** vom Code geschrieben werden, der `strip.setPixelColor` aufruft und alle Pixel einschaltet.

+ Kannst du in deiner neuen Funktion sehen, dass es ein weiteres Paar ** geschweifte Klammern** mit einen Code dazwischen gibt? Dieses Paar gehört zu einer sogenannten **for loop** \(aber nicht die `loop` -Funktion!\). Es sieht so aus:

``` 
    for(uint16_t i=0; i<strip.numPixels(); i++) {

    }
```

--- collapse ---
---
title: Wie funktioniert der Code?
---

Der obige Code überprüft, wie viele NeoPixel sich in deiner Kette befinden, und führt den Code dann so oft in geschweiften Klammern aus.

**Hier das Schlaue:** Der Wert von `i` beginnt als `0` und ändert sich um `1` jedes Mal, also jedes Mal, wenn die Zeile `strip.setPixelColor(i, c);` startet, setzt es die Farbe des **nächsten** Pixels!

--- /collapse ---

+ Zeit, etwas mit diesem zweiten Parameter zu tun! In deiner `animateOneColour` -Funktion, füge die folgende Zeile unter der Zeile `strip.show();` hinzu:

```
    delay(wait);
```

Stelle sicher, dass die neue Zeile **über** der ersten `}` ist, sodass es innerhalb der For-Schleife ist. Dein Text sollte jetzt so aussehen:

``` 
    void animateOneColour(uint32_t c, uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, c);
            strip.show();
            delay(wait);
        }
    }
```

Anstatt eine bestimmte Nummer für das `delay `zu verwenden, benutze den zweiten Parameter deiner Funktion. Dies bedeutet, dass du einen anderen Wert für das `delay` jedes Mal auswählen kannst, wenn du die Funktion aufrufst.

+ Füge deiner Funktion innerhalb des `loop` einen weiteren Aufruf hinzu, damit sich die NeoPixel aus und wieder ein schalten:

    ```
        void loop() {
            animateOneColour(strip.Color(0, 0, 255), 100);
            animateOneColour(strip.Color(0, 0, 0), 100);
        }
    ```

+ Überprüfe deinen Code erneut und laden ihn ins Sketch zur Flora hoch. Jetzt hast du eine coole animierte Sequenz!

Natürlich musst du die NeoPixel nicht ausschalten. Wie wäre es, wenn sie alle nacheinander in einer Reihe von Farben leuchten würden?

```
    void loop() {
        animateOneColour(strip.Color(255, 127, 0), 100);
        animateOneColour(strip.Color(255, 0, 255), 100);
        animateOneColour(strip.Color(0, 255, 255), 100);
    }
```

+ Füge so viele Farben hinzu, wie du möchtest. Versuche, andere Werte als `100` für den zweiten Parameter zu verwenden, und beobachte, wie deine Animation beschleunigt oder verlangsamt wird!
