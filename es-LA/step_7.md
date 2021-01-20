## Anima!

+ Crea la siguiente función nueva en la parte inferior de tu sketch:

``` 
    void animateOneColour(uint32_t c, uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, c);
            strip.show();
        }
    }
```

¿Puedes ver que esta función toma **dos** parámetros en los paréntesis? Más adelante, cambiarás el código de la función para que use el segundo.

+ Elimina el código en la función `loop` y agrega una llamada a tu nueva función:

```
    void loop() {
        animateOneColour(strip.Color(0, 0, 255), 100);
    }
```

¿Notas cómo le estás pasando a la función `animateOneColour` dos parámetros entre paréntesis? Aunque la función todavía no usa el segundo, el código no se compilará si no pasas valores para todos los parámetros cuando llamas a la función.

+ Verifica y carga tu código. ¿Qué puedes notar?

Esta vez solo necesitaste escribir **una línea** de código que llama a `strip.setPixelColor`, y todos los píxeles se encendieron.

+ Dentro de tu nueva función, ¿puedes ver que hay otro par de **llaves** con algo de código en el medio? Este par pertenece a algo llamado **for loop** (bucle for) \(¡pero no a la función `loop`!\). Se ve así:

``` 
    for(uint16_t i=0; i<strip.numPixels(); i++) {

    }
```

--- collapse ---
---
title: ¿Cómo funciona el código?
---

El código anterior verifica cuántos NeoPixels hay en tu cadena y luego ejecuta el código dentro de las llaves la misma cantidad de veces.

**Aquí está la parte inteligente:** El valor de `i` comienza como `0` y aumenta en `1` cada vez, así que cada vez que la línea `strip.setPixelColor (i, c);` se ejecuta, ¡está configurando el color del **siguiente** píxel!

--- /collapse ---

+ ¡Es hora de hacer algo con ese segundo parámetro! En tu función `animateOneColour`, agrega la siguiente línea debajo de la línea `strip.show();`:

```
    delay(wait);
```

Asegúrate de que la nueva línea este **encima** de los primeros `}`, de modo que esté dentro del bucle for (for loop). Tu función debería verse así ahora:

``` 
    void animateOneColour(uint32_t c, uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, c);
            strip.show();
            delay(wait);
        }
    }
```

En lugar de usar un número en particular para el `delay`, estás usando el segundo parámetro de tu función. Esto significa que puedes elegir un valor diferente para el `delay` cada vez que llames a la función.

+ Agrega otra llamada a tu función dentro del `loop` para apagar y encender los NeoPixels:

    ```
        void loop() {
            animateOneColour(strip.Color(0, 0, 255), 100);
            animateOneColour(strip.Color(0, 0, 0), 100);
        }
    ```

+ Verifica tu código nuevamente y carga el sketch en Flora. ¡Ahora tienes una secuencia animada genial!

Por supuesto, no tienes que apagar los NeoPixels. ¿Qué tal hacer que todos se enciendan en un montón de colores uno tras otro?

```
    void loop() {
        animateOneColour(strip.Color(255, 127, 0), 100);
        animateOneColour(strip.Color(255, 0, 255), 100);
        animateOneColour(strip.Color(0, 255, 255), 100);
    }
```

+ Agrega tantos colores como quieras. Intenta pasar también valores distintos de `100` para el segundo parámetro y ¡observa cómo la animación aumenta o disminuye la velocidad!
