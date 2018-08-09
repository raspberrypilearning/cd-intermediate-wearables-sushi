## Colour and light

You're going to write your own **function** now. Functions keep your code tidy. 

+ At the bottom of the sketch, click **after** the `}` \(so, outside the `loop` function\) and press <kbd>Return</kbd> a couple of times. Then type the following code:

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

Note: All the code in a **function** goes in between a pair of **curly braces** `{ }`.

+ Now change your `setup` code so that it looks like this:

``` 
    void setup() {
        // put your setup code here, to run once:
        strip.begin();
        strip.show();
        lightAll();
    }
```

The last line of code **calls** the function you made. That means it tells the function to run.

+ Verify and upload your sketch to the Flora. Did all the pixels light up blue?

--- collapse ---
---
title: Counting out the pixels
---

You might have figured out that the first number in the line `strip.setPixelColor(0, strip.Color(0, 0, 255));` decides which pixel to light up. 

Have you noticed that the first pixel is `0` instead of `1`? So if you have eight pixels, the last one is number `7`.

--- /collapse ---

+ Change the second line of the `lightAll` function from:

```
    strip.setPixelColor(1, strip.Color(0, 0, 255));
``` 

to:

```
    strip.setPixelColor(1, strip.Color(255, 0, 0));
``` 

+ Verify and upload the code to the Flora. Can you spot the difference?

--- collapse ---
---
title: How do colours work in code?
---

On a computer, colours are made by mixing the three **primary colours**: **red**, **green**, and **blue**.

You use numbers from `0` to `255` to tell the computer how much of each colour to mix in. So the code `strip.Color(0, 0, 255)` makes **blue** because the value for red and green are both `0`. 

+ What colour do you think `strip.Color(0, 255, 0)` will give you? Try it out!

--- /collapse ---

Here are a few more colours that are good to know:

```
    void lightAll() {
        strip.setPixelColor(0, strip.Color(0, 0, 255)); // blue
        strip.setPixelColor(1, strip.Color(255, 0, 0)); // red
        strip.setPixelColor(2, strip.Color(0, 255, 0)); // green
        strip.setPixelColor(3, strip.Color(255, 0, 255)); // magenta
        strip.setPixelColor(4, strip.Color(255, 255, 255)); // white
        strip.setPixelColor(5, strip.Color(255, 255, 0)); // yellow
        strip.setPixelColor(6, strip.Color(0, 255, 255)); // cyan
        strip.setPixelColor(7, strip.Color(255, 127, 0)); // orange
        strip.show();
    }
``` 
    
+ Try experimenting with the numbers to get different shades. What do you think you will get if you set a value of `0` for all three colours, `strip.Color(0, 0, 0)`? 

Are you seeing stars yet?! Those NeoPixels sure are BRIGHT, aren't they! 

+ Luckily, if you want to, you can change their brightness with the instruction `strip.setBrightness(10);`. Add it to the `setup` function, in between the lines `strip.begin();` and `strip.show();`. Just like with colours, the number can be anything from `0` to `255`.

--- collapse ---
---
title: Powering lots of NeoPixels
---

You may find that the colours are not showing up properly towards the end of the chain. This is because the circuit is losing power due to **resistance** in the thread. 

+ You can sort this out by stitching an extra thread along both the **negative** and the **positive** tracks in your circuit.

--- /collapse ---
