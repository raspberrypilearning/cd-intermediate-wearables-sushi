## Color y luz

Ahora vas a escribir tu propia **función**. Las funciones mantienen tu código ordenado.

+ En la parte inferior del sketch, haz clic **después** del `}` \(por lo tanto, fuera de la función `bucle`\) y presiona <kbd>Enter</kbd> un par de veces. Luego escribe el siguiente código:

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

Nota: Todo el código en una **función** va entre un par de **llaves** `{ }`.

+ Ahora cambie tu código `setup` para que se vea así:

``` 
    void setup() {
        // coloca tu código de configuración aquí, para que se ejecute una vez:
        strip.begin();
        strip.show();
        lightAll();
    }
```

La última línea del código **llama** la función que creaste. Eso significa que le dice a la función que se ejecute.

+ Verifica y carga tu sketch en Flora. ¿Todos los píxeles se encendieron en azul?

--- collapse ---
---
title: Contando los píxeles
---

Es posible que ya hayas descubierto que el primer número de la línea `strip.setPixelColor (0, strip.Color (0, 0, 255));` decide qué píxel encender.

¿Has notado que el primer píxel es `0` en lugar de `1`? Entonces, si tienes ocho píxeles, el último es el número `7`.

--- /collapse ---

+ Cambia la segunda línea de la función `lightAll` de:

```
    strip.setPixelColor(1, strip.Color(0, 0, 255));
```

a:

```
    strip.setPixelColor(1, strip.Color(255, 0, 0));
```

+ Verifica y carga tu código en el Flora. ¿Notas la diferencia?

--- collapse ---
---
title: ¿Cómo funcionan los colores en el código?
---

En una computadora, los colores se generan mezclando los tres **colores primarios**: **rojo**, **verde** y **azul**.

Se usan los números del `0` a `255` para indicar a la computadora cuánto de cada color debe mezclar. Entonces, el código `strip.Color (0, 0, 255)` genera **azul** porque el valor para el rojo y el verde son ambos `0`.

+ ¿Qué color crees que generará `strip.Color (0, 255, 0)`? ¡Pruébalo!

--- /collapse ---

Aquí hay algunos colores más que es bueno conocer:

```
    void lightAll() {
        strip.setPixelColor(0, strip.Color(0, 0, 255)); // azul
        strip.setPixelColor(1, strip.Color(255, 0, 0)); // rojo
        strip.setPixelColor(2, strip.Color(0, 255, 0)); // verde
        strip.setPixelColor(3, strip.Color(255, 0, 255)); // magenta
        strip.setPixelColor(4, strip.Color(255, 255, 255)); // blanco
        strip.setPixelColor(5, strip.Color(255, 255, 0)); // amarillo
        strip.setPixelColor(6, strip.Color(0, 255, 255)); // cian
        strip.setPixelColor(7, strip.Color(255, 127, 0)); // anaranjado
        strip.show();
    }
```

+ Experimenta con los números para obtener diferentes tonos. ¿Qué crees que obtendrás si estableces un valor de `0` para los tres colores, `strip.Color (0, 0, 0)`?

¡¿Ya estás viendo estrellas?! Esos NeoPixels seguro que son BRILLANTES, ¿no es así?

+ Afortunadamente, si así lo quieres, puedes cambiar ese brillo con la instrucción `strip.setBrightness (10);`. Agrégalo a la función `setup`, entre las líneas `strip.begin ();` y `strip.show ();`. Al igual que con los colores, el número puede ser cualquier número desde `0` a `255`.

--- collapse ---
---
title: Encender muchos NeoPixels
---

Puedes encontrar que los colores no se muestran correctamente hacia el final de la cadena. Esto se debe a que el circuito está perdiendo potencia debido a **la resistencia** en el hilo.

+ Puedes solucionar esto cosiendo un hilo adicional a lo largo de la trayectoria de **negativo** y de **positivo** en tu circuito.

--- /collapse ---
