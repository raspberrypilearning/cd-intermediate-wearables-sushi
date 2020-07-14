## Was du brauchen wirst

### Hardware

+ Adafruit Flora oder Gemma
+ Ein USB-Kabel
+ Rund acht NeoPixel
+ Leitende Fäden
+ Drei Paar Krokoklemmen \ (Du kannst stattdessen auch leitfähige Fadenstücke verwenden, aber Krokoklemme lassen sich möglicherweise leichter testen.)
+ Optional: ein Akku, mit dem Du Dein fertiges Projekt tragen kannst, ohne es an einen Computer anzuschließen!

Die LEDs werden von der Adafruit Flora gesteuert. Du kannst auch ein Adafruit Gemma, LilyPad Arduino oder LilyPad Arduino USB verwenden. In diesem Fall sind einige kleine Codeänderungen erforderlich, z. B. die Nummer des Ausgangspins und das Setup der Karte in der Arduino IDE.

Hinweis: Gemma funktioniert nicht mit dem Linux-Betriebssystem. Es funktioniert auch nicht mit einem USB 3.0-Anschluss, daher musst Du über einen USB 2.0-Anschluss oder Hub verfügen, um das Gemma an den Computer anzuschließen.

### Software

+ Öffne die Arduino IDE

--- zusammenklappen ---
---
Installieren und Einrichten der Arduino IDE
---

+ Lade die Arduino IDE von [ dojo.soy/wear2-arduino-ide herunter ](http://dojo.soy/wear2-arduino-ide) {: target = "_ blank"} und installiere sie.

+ Öffne nach der Installation die Anwendung. Es sind ein paar zusätzliche Dinge erforderlich, damit es für dieses Projekt funktioniert.

+ Öffne die ** -Einstellungen ** vom ** Arduino ** Menu aus. In den ** Zusätzlichen Board Manager-URLs ** füge im Feld Folgendes ein und klicke auf OK.

```
    https://adafruit.github.io/arduino-board-index/package_adafruit_index.json
```

+ Im ** Tools ** Menü gehe zu ** Boards ** und wähle ** Boards Manager... **. Wähle ** Contributed ** aus dem Dropdown-Menü. Installieren Sie ** Adafruit AVR Boards von Adafruit ** . Klicken Sie dann auf ** Schließen ** .

+ Beende die Arduino IDE und starte sie neu. Gehe nochmal ins ** Boards ** Menü und Du solltest ** Adafruit Flora **, ** Adafruit Gemma **, ** LilyPad Arduino ** und ** LilyPad Arduino USB ** aufgeführt sehen. Wähle die Karte aus, die Du verwenden möchtest.

+ Im ** Tools ** Menü gehe zu ** Boards ** und wähle ** Boards Manager... **. Gib ` Neopixel ` in das Suchfeld ein. Installiere ** Adafruit NeoPixel von Adafruit **. Klicke dann auf ** Schließen **.

--- /zusammenklappen ---

### Zusätzliche Materialien

+ Eine Sticknadel und eine Schere
+ Ein T-Shirt
+ Klarer Nagellack
+ Optional: ein Stickrahmen (empfohlen, um das Zusammennähen Ihrer Schaltung zu erleichtern)

