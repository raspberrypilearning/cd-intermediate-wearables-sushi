## Stitch your circuit

+ Gather all your NeoPixels and some chalk or a pencil. Lay a T-shirt \(or whatever piece of fabric you're making your project on\) out on a flat surface.

+ Arrange the pixels into a shape that you like. I'm going to do a smiley face! Some other ideas are:
  + A straight line
  + A heart (eight NeoPixels are perfect for this)
  + Pretend "buttons" down the front of the T-shirt
  + A random pattern

+ Decide roughly where you plan to have the Flora, and choose one NeoPixel for it to be connected to: this will be the first one you sew on. The rest will be connected to each other one by one in a chain.

+ Work out the order in which you will sew the NeoPixels: you should be able to trace a continuous path from the first to the last with your finger in such a way that it does not cross over itself \(this would cause problems with a short circuit!\).

+ Draw around this path with the pencil or chalk, marking the spot where each NeoPixel is.

![](images/drawAroundShape.png)

### Let's start sewing!

+ Once you have everything marked out, set aside all the pieces and grab a needle and some conductive thread. About 20cm should be enough to begin with if your pixels are fairly close together. If you have an embroidery hoop, using it can make the stitching a lot easier.

You will sew the **data** line first. This is the thread that carries the instructions (your code!) telling the NeoPixels what to do, such as when to light up.

+ Take your first NeoPixel and put it in place, with the little arrows pointing towards where the next one will be. Attach it to the fabric by sewing through the hole with the arrow that points **away** from the LED in the centre. This hole is the **output pin**.

--- collapse ---
---
title: Holes or pins?
---

On boards like Adafruit Flora, Arduino, or Raspberry Pi, the little bits of metal you use to connect them to your electrical circuit are called **pins**.

In the case of **wearable** electronics, the pins are not shaped like pins though: they have a hole shape, so that you can connect them with conductive thread. This means that in wearables projects, the words 'pin' and 'hole' can mean the same thing.

--- /collapse ---

+ Be sure to make a secure connection by sewing two or three stitches tightly through the hole.

+ Sew a running stitch to the spot where the next NeoPixel will go.

+ Then take the next pixel and place it onto its spot, with the arrows pointing away from the first one and towards the next spot. Attach it by sewing through the **input** hole \(remember, this is the hole with the arrow pointing **in towards** the LED in the centre\).

+ Secure the thread with a few stitches at the back of the fabric and cut what's left over short.

--- collapse ---
---
title: Protecting the ends
---

It's a good idea to coat the ends of the thread with clear nail polish after cutting, to prevent fraying and avoid stray threads from causing a short circuit.

--- /collapse ---

+ Using a **new piece of conductive thread**, connect the **output** hole of the second NeoPixel to the **input** hole of the third pixel. Continue in this way until all the NeoPixels are chained together along their **data** holes, with a separate piece of thread running in between each pair. The chain ends with the last NeoPixel: you don't attach anything to its **ouptut** hole.

![](images/pixelSewing3_136_800.png)

Next you will connect up all the **negative** holes in the chain, and then all the **positive** ones.

+ Using one long piece of conductive thread, about 50–100cm, sew a few tight stitches through the **-** hole of each pixel, starting with the first one and ending with the last, and sewing a running stitch in between NeoPixels.

**Note**: Make sure the thread does not touch or cross any of the threads in the **data** line!

+ With one more long piece of conductive thread, connect all the **+** holes of the NeoPixels in the same way you just connected the **-** holes.

+ Finally, place the Flora board on the T-shirt \(make sure it is **not plugged in**!\).

+ Using three **separate** pieces of conductive thread, connect the board's **\#6** hole to the **input** hole of the first NeoPixel, the board's **GND** hole to the **-** hole of the first NeoPixel, and the board's **VBATT** hole to the **+** hole of the first NeoPixel, sewing a running stitch along the fabric. Make sure none of the threads touch each other.

+ If you like, you can stitch some of the unused pins of the Flora to the T-shirt with some plain thread to keep it more securely in place.

![](images/stitchedCircuit.png)

+ Now, the moment of truth: plug in your Flora.

You should see all your NeoPixels light up!

--- collapse ---
---
title: Something's not right
---

If some of your NeoPixels didn't light up, don't panic. Some causes could be:

+ A short circuit: are any of the threads touching? Is there anything metallic on the fabric or touching the circuit? Is the fabric wet?

+ Loose connections: The stitches in every hole should be good and tight for a secure connection.

+ Correct code uploaded: Does your code have the right number of NeoPixels defined? Did it compile and upload without errors?

--- /collapse --- 
