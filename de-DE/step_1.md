## Einleitung

Diese Sushi-Karten zeigen Dir, wie du tragbare, programmierbare LEDs verwendest und wie du sie mit einem Code steuern kannst.

**WARNUNG**: Dieses Projekt beinhaltet helle Blinklichter! Es ist möglicherweise nicht geeignet für Epilepsiepatienten.

### Was du machen wirst

In diesem Projekt nähst du LED-Leuchten auf ein T-Shirt und schreibst einen Code, damit sie blinken und sich ihre Farbe ändert!

![Ein buntes Smiley-Gesicht aus LEDs, die auf ein T-Shirt genäht sind](images/rainbowSmile.png)

--- collapse ---
---
title: Was du lernen wirst
---

+ Testen von NeoPixeln
+ Nähen einer NeoPixel-Schaltung mit positivem und negativem Datenfluss
+ Der Ablauf eines Flora-Programms (Setup- und Schleifen-Funktionen)
+ Ein- und Ausschalten von NeoPixeln
+ Adressierung einzelner NeoPixel
+ RGB-Farbmischung
+ Funktionen und Parameter
+ Verwenden von Feedback-Schleifen
+ Erkundung fortgeschrittener Beispiele

--- /collapse ---

--- collapse ---
---
title: Was du brauchen wirst
---

### Hardware

+ Adafruit Flora oder Gemma
+ Ein USB-Kabel
+ Ungefähr acht NeoPixel
+ Leitfähige Fäden
+ Drei Paar Krokodilklemmen (Du kannst stattdessen auch leitfähige Fäden verwenden, aber mit Krokodilklemmen lässt es sich möglicherweise leichter testen)
+ Optional: ein Akku, mit dem du die Möglichkeit hast, dein fertiges Projekt zu tragen, ohne es an einen Computer anzuschließen!

Die LEDs werden von der Adafruit Flora gesteuert. Du kannst auch ein Adafruit Gemma, LilyPad Arduino oder LilyPad Arduino USB verwenden. In diesem Fall sind einige kleine Codeänderungen erforderlich, z. B. die Nummer des Ausgangspins und das Setup der Karte in der Arduino IDE.

Hinweis: Gemma funktioniert nicht mit Linux-Betriebssystem. Es funktioniert auch nicht mit einem USB 3.0-Anschluss, daher musst du über einen USB 2.0-Anschluss oder Hub besitzen, um das Gemma an den Computer anzuschließen.

### Software

+ Die Arduino IDE

### Installieren und Einrichten der Arduino IDE

+ Lade die Arduino IDE von [dojo.soy/wear2-arduino-ide herunter](http://dojo.soy/wear2-arduino-ide){:target="_blank"} und installiere sie.

+ Öffne nach der Installation die Anwendung. Es sind ein paar zusätzliche Dinge erforderlich, damit es für dieses Projekt funktioniert.

+ Öffne die **Voreinstellungen** aus dem **Arduino** Menü `Datei` oder durch die Tastenkombination Strg+Komma. Im Bereich **Zusätzliche Boardverwalter-URLs**, füge Folgendes hinzu und klicke auf OK.

```
    https://adafruit.github.io/arduino-board-index/package_adafruit_index.json
```

+ Gehe im Menü **Werkzeuge** zu **Board:** und wähle **Boardverwalter...** aus. Wähle **Beigetragen** aus dem Dropdown-Menü. Installiere **Adafruit AVR Boards von Adafruit**. Klicke dann auf **Schließen**.

+ Beende die Arduino IDE und starte sie neu. Gehe zum Menü **Board:** und du solltest die **Adafruit Flora**, **Adafruit Gemma**,**LilyPad Arduino** und **LilyPad Arduino USB** aufgeführt sehen. Wähle die Karte aus, die du verwenden möchtst.

+ Gehe im Menü **Sketch** zu **Bibliothek einbinden** und wähle **Bibliotheken verwalten**. Gib `Neopixel` in das Suchfeld ein. Installiere **Adafruit NeoPixel by Adafruit**. Klicke dann auf **Schließen**.

### Zusätzliche Materialien

+ Eine Sticknadel und eine Schere
+ Ein T-Shirt
+ Klarer Nagellack
+ Optional: ein Stickrahmen (empfohlen, um das Zusammennähen deiner Schaltung zu erleichtern)

--- /collapse ---