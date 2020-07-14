## Schreibe deinen eigenen Code

+ Klicke in der Arduino IDE auf **Datei** und dann **Neu**. Du erhälst eine leere **Sketch**, die so aussieht:
```
    void setup() {
        // Gib deinen Setup-Code hier ein, um ihn einmal auszuführen:

    }
    void loop() {
        // Gib deinen Hauptcode hier ein, um ihn wiederholt auszuführen:

    }
```

--- collapse ---
---
title: Notizen in deinem Code machen
---

Jede Zeile, die mit `//` beginnt ist ein **Kommentar**. Kommentare werden vom Computer ignoriert.

Sie sind nützlich, um Notizen für sich selbst oder für andere Personen zu machen, die deinen Code verwenden möchten!

--- /collapse ---

+ Gehe zu **Sketch** and dann auf **Bibliothek einbinden** und wähle **Adafruit NeoPixel**. Du solltest sehen, dass dieser Code oben in deinem Sketch hinzugefügt wird: `#include<Adafruit_NeoPixel.h>`.

+ Klicke an das Ende der Zeile und drücke die <kbd>Eingabe</kbd>-Taste einige Male, um einige leere Zeilen darunter hinzuzufügen.

+ Tippe unter der neuen Codezeile Folgendes ein: `#define PIXELS_PIN 6`

Mit diesem Code legst du fest, welcher Pin (das Gleiche hier wie ein Loch, denke daran) der Flora für **Daten** verwendet werden soll (Anleitung). Daher ist der Pin, den du mit den **Daten**-Löchern der NeoPixel verbindest die Nummer **6**.

+ Gib darunter `#define NUM_PIXELS 8` ein. Dies ist die Anzahl der NeoPixel, die du hast. Wenn du eine andere Nummer als acht hast, gib diese Nummer anstelle von `8` ein.

+ Gib schließlich darunter ein:

``` 
    Adafruit_NeoPixel strip = Adafruit_NeoPixel(NUM_PIXELS, PIXELS_PIN, NEO_GRB + NEO_KHZ800);
```

+ Innerhalb der `setup`-Funktion, füge die folgenden zwei Zeilen hinzu:

``` 
    void setup() {
        // Gib deinen Setup-Code hier ein, um ihn einmal auszuführen:
        strip.begin();
        strip.show();
    }
```

--- collapse ---
---
title: Was ist die Setup-Funktion?
---

Der Code `void setup ()` definiert die `setup`-Funktion. Dies ist ein Codeblock, der ausgeführt wird, wenn die Flora angeschaltet ist.

Der gesamte Code zwischen den geschweiften Klammern `{`und`}` ist in der Funktion und wird durchlaufen, wenn die Flora eingeschaltet wird.

--- /collapse ---

+ Nach `strip.show();` drücke <kbd>Eingabe</kbd> und gib diese beiden Zeilen ein:

``` 
    strip.setPixelColor(0, strip.Color(0, 0, 255));
    strip.show();
```

+ Klicke auf **Überprüfen**, um deinen Code zu kompilieren und auf Fehler zu prüfen. Wenn es Fehler gibt, musst du den Code korrigieren und erneut überprüfen. Normalerweise sagen dir die Fehlermeldungen, welche Codezeile repariert werden muss. Überprüfe, ob du es genau, wie gezeigt, eingegeben hast!

+ Lass uns die Flora in eine Steckdose einstecken und deinen Code ausführen! Drücke den **Reset**-Knopf auf der Flora und dann drücke auf die **Hochladen**-Taste. Was passiert, wenn es fertig ist?

Du solltest das erste Pixel blau aufleuchten sehen.

+ Lass uns noch einen machen! Gib **über** dem zweiten `strip.show();` zwei weitere Zeilen ein:

```
    strip.setPixelColor(1, strip.Color(0, 0, 255));
    strip.setPixelColor(2, strip.Color(0, 0, 255));
```

Die `setup`-Funktion sollte jetzt so aussehen:

``` 
    void setup() {
        // Gib deinen Setup-Code hier ein, um ihn einmal auszuführen:
        strip.begin();
        strip.show();
        strip.setPixelColor(0, strip.Color(0, 0, 255));
        strip.setPixelColor(1, strip.Color(0, 0, 255));
        strip.setPixelColor(2, strip.Color(0, 0, 255));
        strip.show();
    }
```

Kannst du herausfinden, was einiges von diesen Code macht?

+ Überprüfe deinen Code und lade ihn erneut hoch. Du solltest die ersten drei Pixel blau aufleuchten sehen.

+ Versuche, ob du weitere Codezeilen hinzufügen kannst, damit auch die restlichen Pixel aufleuchten!

![](images/threeBlue.png)


