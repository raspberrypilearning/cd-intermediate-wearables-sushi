## Lo que necesitarás

### Hardware

+ Adafruit Flora o Gemma
+ Un cable USB
+ Alrededor de ocho NeoPixels
+ Cable conductor
+ Tres pares de pinzas cocodrilo \(también puedes usar trozos de cable conductor, pero las pinzas cocodrilo pueden ser más fáciles de usar\)
+ Opcional: una batería, ¡que le permitirá usar su proyecto terminado sin que esté conectado a una computadora!

Los LED serán controlados por Adafruit Flora. También puedes usar un Adafruit Gemma, LilyPad Arduino o LilyPad Arduino USB; si lo haces, se necesitarán algunos pequeños cambios en el código, como el número del pin de salida y la configuración de la placa en el IDE de Arduino.

Nota: Gemma no funciona con el sistema operativo Linux. Tampoco funcionará con un puerto USB 3.0, por lo que debe tener un puerto o concentrador USB 2.0 para conectar el Gemma a la computadora.

### Software

+ El IDE de Arduino

--- collapse ---
---
title: Instalando y configurando el IDE Arduino
---

+ Descarga el IDE de Arduino desde [ dojo.soy/wear2-arduino-ide ](http://dojo.soy/wear2-arduino-ide) {:target = "_ blank"} e instálalo.

+ Una vez que esté instalado, abre la aplicación. Hay algunos ajustes adicionales necesarios para hacerlo funcionar para este proyecto.

+ Abra **Preferences** en el menú de **Arduino**. En el recuadro **Additional Board Manager URLs**, pega lo siguiente y da click en OK.

```
    https://adafruit.github.io/arduino-board-index/package_adafruit_index.json
```

+ En el menú **Tools**, dirígete a **Boards** y selecciona **Boards Manager...**. Selecciona **Contributed** en el menú desplegable. Instala **Adafruit AVR Boards by Adafruit**. Luego haz click en **Close**.

+ Sal y reinicia el IDE de Arduino. Ve al menú **Boards** nuevamente, deberías ver el **Adafruit Flora**, **Adafruit Gemma**, **LilyPad Arduino**, y **LilyPad Arduino USB** en la lista. Selecciona el tablero que usarás.

+ En el menú **Sketch**, ve a **Include Library** y selecciona **Manage Libraries...**. Escribe `neopixel` en el recuadro de búsqueda. Instala **Adafruit NeoPixel by Adafruit**. Luego haz click en **Close**.

--- /collapse ---

### Materiales adicionales

+ Una aguja de bordar y tijeras
+ Una camiseta
+ Esmalte de uñas transparente
+ Opcional: un aro de bordado (recomendado para facilitar la costura de tu circuito)

