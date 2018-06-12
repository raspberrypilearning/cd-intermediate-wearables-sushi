## Write your own code

+ In Arduino IDE, click **File** &gt; **New**. You will get a blank **sketch** that looks like this 
```
    void setup() {
        // put your setup code here, to run once:

    }
    void loop() {
        // put your main code here, to run repeatedly:

    }
```

--- collapse ---
---
title: Making notes in your code
---

Any line that starts with `// ` is a **comment**. 

Comments are ignored by the computer. 

They're useful for making notes for yourself or other people reading the code.

--- /collapse ---

+ Go to **Sketch** &gt; **Include Library** and select **Adafruit NeoPixel**. You should see this code get added to the top of your sketch: `#include <Adafruit_NeoPixel.h>`. Click at the end of the line and hit Return a few times to add some blank lines underneath.

+ Underneath the new line of code, type the following: `#define PIXELS_PIN 6` You are setting which pin of the Flora to use for **data** \(instructions\). That's the pin you connect the **data** pins of the pixels to, pin number 6.

+ Underneath that, type `#define NUM_PIXELS 8`. This is the number of NeoPixels you have. If you have a different number than 8, type that number instead of 8.

+ Finally, underneath that, type 

``` 
    Adafruit_NeoPixel strip = Adafruit_NeoPixel(NUM_PIXELS, PIXELS_PIN, NEO_GRB + NEO_KHZ800);
```

+ Inside the `setup` function, add the following two lines

``` 
    void setup() {
        // put your setup code here, to run once:
        strip.begin();
        strip.show();
    }
```

--- collapse ---
---
title: What is the setup function?
---

The code `void setup ()` defines the `setup` function.

This is a block of code that runs when the Flora starts.

All the code in between the curly braces `{` and `}` is in the function and so will run when the Flora starts.

--- /collapse ---

+ After `strip.show();`, press return and type these two lines underneath

``` 
    strip.setPixelColor(0, strip.Color(0, 0, 255));
    strip.show();
```

+ Click **Verify** to compile your code and check for errors. If there are any mistakes you will need to fix the code and check again. Usually the errors tell you which line of code needs fixing. Check that you typed it exactly as shown!

+ Let's plug in the Flora and run your code! Press the **reset** button on the Flora and then click the **Upload** button. When it's done, what happens?

Hopefully, you should see the first pixel light up blue. 

+ Let's do another! **Above** the second `strip.show();` type two more lines:

```
    strip.setPixelColor(1, strip.Color(0, 0, 255));
    strip.setPixelColor(2, strip.Color(0, 0, 255));
``` 

The `setup` function should look like this now:

``` 
    void setup() {
        // put your setup code here, to run once:
        strip.begin();
        strip.show();
        strip.setPixelColor(0, strip.Color(0, 0, 255));
        strip.setPixelColor(1, strip.Color(0, 0, 255));
        strip.setPixelColor(2, strip.Color(0, 0, 255));
        strip.show();
    }
```

Can you work out what some of this code is doing?

+ Verify and upload your code once more. This time you should see the first three pixels light up blue. 

+ See if you can add more lines of code to make the rest of the pixels light up as well! 

![](images/threeBlue_150_800.png)


