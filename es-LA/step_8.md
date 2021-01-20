## Diversión colorida

+ Agrega la siguiente función nueva al final de tu sketch. No te preocupes, ¡no tienes que entenderlo ahora! Se tomó prestado del sketch de ejemplo que ejecutaste anteriormente.


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

Esta función te permite elegir cualquier número entre `0` y `255`, y mezcla un color por ti.

+ Ahora agrega otra función nueva. ¡Ve si puedes detectar el **for loop** en él!

```
    void lightAllRainbow() {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels())) & 255));
            strip.show();
        }
    }
```

¡Hay un poco de matemáticas aquí! Está ahí para hacer una buena selección de colores uniformemente a lo largo de todo el arco iris.

+ Todo lo que queda es llamar a la función. Cambia la función `loop` para que solo tenga esta línea de código. Luego verifica y carga tu sketch para ver un hermoso arco iris de colores.

```
    void loop() {
        lightAllRainbow();
    }
```

No necesitas pasar ningún parámetro esta vez, ¡porque la nueva función determina los colores por ti!

+ ¿Qué tal agregar un delay? Escribamos una nueva función que sea similar a la anterior, pero con un delay agregado al loop para que anime tus NeoPixels:

```
    void animateRainbow(uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels())) & 255));
            strip.show();
            delay(wait);
        }
    }
```

+ Cambia la llamada a la función en la función `loop` y agrega una segunda línea de código para llamar a tu otra función `animate` también:

```
    void loop() {
        animateRainbow(100);
        animateOneColour(strip.Color(0, 0, 0), 100);
    }
```

¡Pruébalo en Flora!

--- challenge ---

## Desafío: intenta crear tus propias secuencias

+ Intenta combinar varias llamadas diferentes a la función `animateRainbow` y tus otras funciones. ¡Tu imaginación pone el limite!

+ Puedes hacer un montón de cosas interesantes utilizando los trucos que haz aprendido con colores, bucles (loops) y retrasos (delays). Si quieres ver algunos ejemplos más, consulta el sketch **strandtest** que usaste para probar los NeoPixels.

--- /challenge ---

--- collapse ---
---
title: Energía portátil
---

Si planeas llevar puesto tu proyecto, probablemente querrás hacerlo más portátil usando la energía de una batería.

+ Para Flora, un paquete de baterías 3×AA o uno de 3×AAA funcionará bien. Consulta [dojo.soy/wear2-flora-power](http://dojo.soy/wear2-flora-power){:target="_blank"} para más información.

+ Si está utilizando un tablero diferente, debes verificar los requisitos de energía que tiene.

--- /collapse ---


***
Este proyecto fue traducido por voluntarios:

Verónica Valencia Límaco

Carlos Yalta Vargas

Gracias a los voluntarios, podemos dar a las personas de todo el mundo la oportunidad de aprender en su propio idioma. Puedes ayudarnos a llegar a más personas ofreciéndote como voluntario para traducir. Más información en [rpf.io/translate](https://rpf.io/translate).
