## What you will need

### Hardware

+ Adafruit Flora or Gemma and a USB cable
+ Around eight NeoPixels
+ Conductive thread
+ Three pairs of crocodile clips \(you can also use pieces of conductive thread instead, but crocodile clips may be easier to test with\)
+ Optional: a battery pack will allow you to wear your finished project without being attached to the computer!

The LEDs will be controlled by the Adafruit Flora. You may also use an Adafruit Gemma, LilyPad Arduino or LilyPad Arduino USB; some small code changes will be needed such as the number of the output pin and the board setup in the Arduino IDE.

Note: the Gemma does not work with Linux. It also won't work with a USB 3.0 port, so you must have a USB 2.0 port or hub to connect the Gemma to the computer.

### Software

+ Arduino IDE

--- collapse ---
---
title: Installing and setting up Arduino IDE
---

+ Download and install the Arduino IDE from [dojo.soy/wear2-arduino-ide](http://dojo.soy/wear2-arduino-ide){:target="_blank"}. Once installed, open the application. There a few extra things needed to make it work for this project.

+ Open the **Preferences** from the **Arduino** menu. In the **Additional Board Manager URLs** box, paste the following and click OK.

```
    https://adafruit.github.io/arduino-board-index/package_adafruit_index.json
```

+ In the **Tools** menu, go to **Board** and select **Boards Manager...**. Choose **Contributed** from the dropdown. Install **Adafruit AVR Boards by Adafruit**. Click Close.

+ Quit and restart Arduino IDE. You should see the **Adafruit Flora** and the **Adafruit Gemma** listed in the **Boards** menu now as well as the **LilyPad Arduino** and **LilyPad Arduino USB**. Select the board you will be using.

+ In the **Sketch** menu, go to **Include Library** and select **Manage Libraries...**. Type `neopixel` into the search box. Install **Adafruit NeoPixel by Adafruit**. Click Close.

--- /collapse ---

### Additional materials

+ An embroidery needle and scissors
+ A t-shirt
+ Clear nail polish
+ Optional: an embroidery hoop is recommended to make stitching up your circuit easier

