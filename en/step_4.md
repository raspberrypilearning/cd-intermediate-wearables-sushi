## Stitching your circuit

+ Gather all your NeoPixels and some chalk or a pencil. Lay a t-shirt \(or whatever piece of fabric you're making the project on\) out on a flat surface. Arrange the pixels into a shape that you like. I'm going to do a smiley face! Some other ideas are
 + A straight line
 + A heart (eight NeoPixels is perfect for this)
 + Pretend "buttons" down the front of a t-shirt

+ Decide roughly where you plan to have the Flora and choose one NeoPixel for it to be connected to: this will be the first one you start sewing on. The rest will be connected to each other one by one in a chain. You should be able to trace a continuous line along the chain with your finger in such a way that it does not cross over itself \(this would cause problems with a short circuit!\)

+ Draw around the outside and the inside of the shape with the pencil or chalk, marking the spot where each NeoPixel is.

![](images/drawAroundShape_178_800.png)

+ Ready to start sewing? Once you have everything marked out, set aside all the pieces and grab a needle and some conductive thread. About 20cm should be enough to begin with if your pixels are quite close together. If you have an embroidery hoop, it can make the stitching a lot easier.

+ You will sew the **data** line first. Take your first pixel and put it in place, with the little arrows pointing towards where the next one will be. Attach it to the fabric by sewing through the pin with the arrow that points **away** from the LED in the centre. This is the **output** pin. 
 * Be sure to make a secure connection by sewing three or four stitches tightly through the pin.
 
+ Sew a running stitch to the spot where the next pixel will go. Then take the next pixel and place it onto its spot, with the arrows pointing away from the first one and towards the next spot. 

+ Attach it by sewing through the **input** pin \(remember, this is the pin with the arrow pointing **in towards** the LED in the centre\). Secure the thread with a few stitches at the back of the fabric and cut it short.

--- collapse ---
---
title: Protecting the ends
---

It's a good idea to coat the ends of the thread with clear nail polish after cutting, to prevent fraying and avoid stray threads from causing a short circuit.

--- /collapse ---

+ Using a **new piece of conductive thread**, connect the **output** pin of the second pixel to the **input** pin of the third pixel. Continue in this way until all the pixels are chained together along their **data** pins, with a separate piece of thread running in between each pair. The chain ends with the last pixel: you don't attach anything to its **ouptut** pin.
 
![](/images/pixelSewing3_136_800.png)
 
+ Next you will connect up all the **negative** pins in the chain, this time using one long piece of conductive thread, about 50-100cm. Sew a few tight stitches through the **-** pin of each pixel starting with the first one and ending with the last. As usual sew with a running stitch in between pixels. 
Note: Make sure the thread does not touch or cross any of the thread in the **data** line!

+ With one more long piece of conductive thread, connect all the **+** pins of the pixels in the same way you just connected the **-** pins.

+ Finally, place the Flora on the t-shirt \(make sure it is **not plugged in**!\). Using three separate pieces of conductive thread, connect the **#6** pin to the **input**, the **GND** pin to the **-**, and the **VBATT** pin to the **+** pin of that first NeoPixel, sewing a running stitch along the fabric. Make sure none of the threads touch each other. 

+ If you like, you can stitch some of the unused pins of the Flora to the t-shirt with some plain thread to keep it more securely in place.

![](/images/stitchedCircuit_200_800.png)

+ It's the moment of truth... plug in your Flora! 

--- collapse ---
---
title: Something's not right
---

If your pixels didn't all light up, don't panic. Some causes could be: 

+ A short circuit: are any of the threads touching? Is there anything metallic on the fabric or touching the circuit? Is the fabric wet?

+ Loose connections: The stitches at every pin should be good and tight for a secure connection

+ Correct code uploaded: Does your code have the right number of pixels defined? Did it compile and upload without errors?

--- /collapse --- 



