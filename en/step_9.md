## Rainbow fun

+ Add the following new function to the end of your sketch. Don't worry, you don't have to understand it just now! It's borrowed from the example sketch you ran earlier. 


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

This function lets you choose any numer from 0 to 255 and it mixes a colour for you.

+ Now add another new function. See if you can spot the **for loop** in it!

```
    void lightAllRainbow() {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels())) & 255));
            strip.show();
        }
    }
```

There's a bit of math in here too! It's there to pick a nice selection of colours evenly from across the whole rainbow.

+ All that's left is to **call** the function. Change the `loop` function so that it has just this line of code in it. Then verify and upload your sketch to see a lovely rainbow of colours.

```
    void loop() {
        lightAllRainbow();
    }
``` 

You don't need to pass any **parameters** this time because the new function figures out the colours for you! 

+ How about adding a delay? Let's write a new function, that's similar to the one above but with a delay added to the loop so it animates:

```
    void animateRainbow(uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels())) & 255));
            strip.show();
            delay(wait);
        }
    }
```

+ Change the function call in the `loop` function and add a second line of code to call your other animate function too:

```
    void loop() {
        animateRainbow(100);
        animateOneColour(strip.Color(0, 0, 0), 100);
    }
``` 

Try it out on the Flora!

--- challenge ---

## Challenge: Try making your own sequences

+ Have a go at combining various different calls to the `animateRainbow` function and your other functions. Your imagination is the limit! 

+ You can do loads of cool things using the tricks you've learned with colours, loops and delays. If you want to see some more examples, check out the **strandtest** sketch that you used to test out the NeoPixels. 

![](images/rainbowSmile.png)

--- /challenge ---

--- collapse ---
---
title: Portable power
---

+ If you plan on wearing your project, you will probably want to make it more portable with battery power. A 3xAA or 3xAAA battery pack will do just fine for the Flora. 

+ See [dojo.soy/wear2-flora-power](http://dojo.soy/wear2-flora-power){:target="_blank"} for more information. 

+ For other boards you should double check the requirements for the board you are using.

--- /collapse ---