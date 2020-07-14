## Farbe und Licht

Du wirst jetzt deine eigene **Funktion** schreiben. Funktionen halten deinen Code aufgeräumt.

+ Klicke im unteren Teil im Sketch **hinter** dem `}` (also außerhalb der `loop`-Funktion) und drücke <kbd>Eingabe</kbd> ein paar Mal. Gib den folgenden Code ein:

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

Hinweis: Der gesamte Code in einer **Funktion** befindet sich zwischen ein Paar **geschweiften Klammern** `{ }`.

+ Ändere nun deinen `setup`-Code, damit es so aussieht:

``` 
    void setup () {
        // gebe deinen Setup-Code hier ein, um ihn einmal auszuführen:
        strip.begin ();
        strip.show ();
        lightAll ();
    }
```

Die letzte Codezeile **ruft** die Funktion auf, die du erstellt hast. Das heißt, es weist der Funktion an, ausgeführt zu werden.

+ Überprüfe deinen Sketch und lade es in die Flora hoch. Haben alle Pixel blau geleuchtet?

--- collapse ---
---
title: Pixel zählen
---

Möglicherweise hast du herausgefunden, dass die erste Zahl in der Zeile `strip.setPixelColor(0, strip.Color(0, 0, 255)); ` entscheidet, welches Pixel aufleuchtet.

Hast du bemerkt, dass das erste Pixel `0` anstelle von `1` ist? Wenn du also acht Pixel hast, ist das letzte die Nummer `7`.

--- /collapse ---

+ Ändere die zweite Zeile der `lightAll` Funktion von:

```
    strip.setPixelColor(1, strip.Color(0, 0, 255));
```

zu:

```
    strip.setPixelColor(1, strip.Color(255, 0, 0));
```

+ Überprüfe dein Sketch und lade es in die Flora hoch. Erkennst du den Unterschied?

--- collapse ---
---
title: Wie funktionieren Farben im Code?
---

Auf einem Computer werden Farben durch Mischen der drei **Primärfarben**: **rot**, **grün** und **blau** erstellt.

Du verwendest Zahlen von `0` bis `255`, um dem Computer mitzuteilen, wie viel von jeder Farbe eingemischt werden soll. Daher macht der Code `strip.Color(0, 0, 255)` **blau**, weil die Werte für Rot und Grün beide `0` sind.

+ Welche Farbe denkst du wird dir `strip.Color(0, 255, 0)` geben? Versuch es!

--- /collapse ---

Hier sind einige weitere Farben, die gut zu merken sind:

```
    void lightAll() {
        strip.setPixelColor(0, strip.Color(0, 0, 255)); // blau
        strip.setPixelColor(1, strip.Color(255, 0, 0)); // rot
        strip.setPixelColor(2, strip.Color(0, 255, 0)); // grün
        strip.setPixelColor(3, strip.Color(255, 0, 255)); // Magenta
        strip.setPixelColor(4, strip.Color(255, 255, 255)); // weiß
        strip.setPixelColor(5, strip.Color(255, 255, 0)); // gelb
        strip.setPixelColor(6, strip.Color(0, 255, 255)); // Cyan
        strip.setPixelColor(7, strip.Color(255, 127, 0)); // orange
        strip.show();
    }
```

+ Versuche, mit den Zahlen zu experimentieren, um verschiedene Farbtöne zu erhalten. Was erhälst du, wenn du den Wert `0` für alle drei Farben, `strip.Color(0, 0, 0)`, festlegst?

Siehst du schon Sterne?! Diese NeoPixel sind sicher HELL, nicht wahr?

+ Glücklicherweise kannst du die Helligkeit mit der Anweisung `strip.setBrightness(10);` ändern, wenn du möchtest. Füge es zu der `setup`-Funktion zwischen den Zeilen `strip.begin();` und `strip.show();` hinzu. Genau wie bei Farben kann die Zahl zwischen `0` und `255` liegen.

--- collapse ---
---
title: Stromversorgung vieler NeoPixel
---

Möglicherweise werden die Farben gegen Ende der Kette nicht richtig angezeigt. Dies liegt daran, dass die Schaltung aufgrund des **Widerstands** in den Fäden an Leistung verliert.

+ Du kannst dies beheben, indem du einen zusätzlichen Faden entlang der **negativen** und der **positiven** Wege in deiner Schaltung nähst.

--- /collapse ---
