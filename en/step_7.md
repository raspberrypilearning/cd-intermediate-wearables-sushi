## Flashing lights

+ Create the following new function after your first one:

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
title: What's inside the brackets?
---

This function takes a **parameter**: that's the bit inside the round brackets. It's some extra information that you give the function when you call it.

--- /collapse ---

+ This time you will write your function calls in `loop` instead of in `setup`. Click inside the `loop` function and add code so that it looks like this:

```
    void loop() {
        lightAllOneColour(strip.Color(0, 0, 255));
        delay(200);
        lightAllOneColour(strip.Color(0, 0, 0));
        delay(200);
    }
```

See how you're passing in a colour as a **parameter** to your function? This is the colour that gets used in place of `c` on each line of your function `lightAllOneColour`. It means you can use the same function to make the pixels any colour, even to turn them all off!

+ Delete the line `lightAll();` from inside the `setup` function. Verify and upload the code.

--- collapse ---
---
title: setup and loop
---

When the Flora starts, it runs all the code in the `setup` function first and then it runs the `loop` function over and over again forever!

--- /collapse ---

+ What do you think the **delay** function does? Try putting in different values for it's **parameter**. For example, `delay(50);` or `delay(1000);`. Don't forget to verify and upload the code to test out your changes!

+ Have you noticed that the colour `(0, 0, 0)` turns the pixels off? Try running the following code on the Flora:

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

+ Now run the same code without the "off" colour:

```
    void loop() {
        lightAllOneColour(strip.Color(255, 0, 255));
        delay(500);
        lightAllOneColour(strip.Color(255, 127, 0));
        delay(500);
    }
```

+ Do you see the difference?

--- challenge ---

## Challenge: design your own sequence

+ Try designing your own sequence by changing the code in the **loop** function! You can add as many delays and as many calls to your **lightAllOneColour** function as you like. Experiment with longer and shorter delays and different values for the colour parameter.

Remember, the whole sequence will keep repeating over and over. 

--- /challenge ---