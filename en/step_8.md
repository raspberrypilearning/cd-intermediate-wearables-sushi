## Animate!

+ Create the following new function at the bottom of your sketch:

``` 
    void animateOneColour(uint32_t c, uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, c);
            strip.show();
        }
    }
```

Can you see that this function takes **two** parameters in the round braces? Later on, you'll change the function's code so it uses the second one.

+ Delete the code in the `loop` function and add in a call to your new function:

```
    void loop() {
        animateOneColour(strip.Color(0, 0, 255), 100);
    }
``` 

Notice how you're passing the `animateOneColour` function two parameters in the brackets? Even though the function doesn't use the second one just yet, but the code won't compile if you don't pass in values for all the parameters when you call the function.

+ Verify and upload your code. What do you notice?

This time you only needed to write **one line** of code that calls `strip.setPixelColor`, and all of the pixels turned on. 

+ Inside your new function, can you see that there is another pair of **curly braces** with some code in between? This pair belongs to something called a **for loop** \(but not the `loop` function!\). It looks like this:

``` 
    for(uint16_t i=0; i<strip.numPixels(); i++) {
        
    }
```

--- collapse ---
---
title: How does the code work?
---

The above code checks how many NeoPixels are in your chain and then runs the code inside the curly braces that many times. 

**Here's the clever bit:** The value of `i` starts off as `0` and changes by `1` each time, so every time the line `strip.setPixelColor(i, c);` runs, it's setting the colour of the **next** pixel!

--- /collapse ---

+ Time to do somthing with that second parameter! In your `animateOneColour` function, add the following line below the line `strip.show();`:

```
    delay(wait);
```

Make sure the new line is **above** the first `}`, so that it's inside the for loop. Your function should look like this now:

``` 
    void animateOneColour(uint32_t c, uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, c);
            strip.show();
            delay(wait);
        }
    }
```

Instead of using a particular number for the `delay`, you are using the second parameter of your function. This means you can choose a different value for the `delay` each time you call the function. 

+ Add another call to your function inside `loop` to turn the NeoPixels off as well as on:

    ```
        void loop() {
            animateOneColour(strip.Color(0, 0, 255), 100);
            animateOneColour(strip.Color(0, 0, 0), 100);
        }
    ``` 

+ Verify your code again and upload the sketch to the Flora. Now you have a cool animated sequence!

Of course, you don't have to turn the NeoPixels off. How about making them all light up in a bunch of colours one after the other?

```
    void loop() {
        animateOneColour(strip.Color(255, 127, 0), 100);
        animateOneColour(strip.Color(255, 0, 255), 100);
        animateOneColour(strip.Color(0, 255, 255), 100);
    }
``` 

+ Add as many colours as you like. Try passing in different values other than `100` for the second parameter as well, and watch your animation speed up or slow down!
