## Stik je circuit

+ Verzamel al je NeoPixels en wat krijt of een potlood. Leg een T-shirt \(of welk ander stuk stof waar je je project op maakt\) op een vlakke ondergrond.

+ Rangschik de pixels in een vorm die je leuk vindt. Ik ga een smiley-gezicht doen! Andere ideeën zijn:
  + Een rechte lijn
  + Een hart (acht NeoPixels zijn hier perfect voor)
  + Doe alsof "knopen" aan de voorkant van het T-shirt
  + Een willekeurig patroon

+ Bepaal ruwweg waar je de Flora wilt hebben en kies een NeoPixel waarmee je de Flora wilt verbinden: Dit is de eerste die je naait. De rest wordt een voor een in een keten met elkaar verbonden.

+ Werk de volgorde uit waarin je de NeoPixels naait: Je zou een continu pad van de eerste naar de laatste met je vinger moeten kunnen volgen, zodat het zichzelf niet kruist \(dit zou problemen met een kortsluiting veroorzaken!\).

+ Teken rond dit pad met het potlood of krijt en markeer de plek waar elke NeoPixel is.

![](images/drawAroundShape.png)

### Laten we beginnen met naaien!

+ Als alles is gemarkeerd, leg je alle stukjes opzij en pak je een naald en wat geleidende draad. Ongeveer 20cm zou genoeg moeten zijn om mee te beginnen als je pixels vrij dicht bij elkaar liggen. Als je een borduurhoepel hebt, kan het gebruik ervan het stikken een stuk gemakkelijker maken.

Je naait eerst de **data**-lijn. Dit is de draad die de instructies bevat (jouw code!) die de NeoPixels vertellen wat ze moeten doen, zoals wanneer ze moeten oplichten.

+ Neem je eerste NeoPixel en zet hem op zijn plaats, met de kleine pijlen die wijzen naar de plaats waar de volgende komt. Bevestig het aan de stof door het gat te naaien met de pijl die **weg** wijst van de LED in het midden. Dit gat is de **uitgangspen**.

--- collapse ---
---
title: Gaten of spelden?
---

Op borden zoals Adafruit Flora, Arduino of Raspberry Pi worden de kleine stukjes metaal die je gebruikt om ze aan te sluiten op je elektrische circuit **pinnen** genoemd.

In het geval van **draagbare** elektronica, zijn de pinnen echter niet als pinnen gevormd: Ze hebben een gatenvorm, zodat je ze kunt verbinden met geleidende draad. Dit betekent dat in draagbare projecten de woorden 'pin' en 'hole' (gat) hetzelfde kunnen betekenen.

--- /collapse ---

+ Zorg ervoor dat je een veilige verbinding maakt door twee of drie steken strak door het gat te naaien.

+ Naai een rijgsteek naar de plek waar de volgende NeoPixel komt.

+ Neem vervolgens de volgende pixel en plaats deze op zijn plek, met de pijlen weg van de eerste en naar de volgende plek. Bevestig het door het door het **input**-gat te naaien \(vergeet niet dat dit het gat is met de pijl **in de rechting van** de LED in het midden).

+ Zet de draad vast met een paar steken aan de achterkant van de stof en knip wat er overblijft kort af.

--- collapse ---
---
title: Het beschermen van de uiteinden
---

Het is een goed idee om de uiteinden van de draad na het afknippen met een heldere nagellak te bedekken, om rafelen te voorkomen en te voorkomen dat verdwaalde draden kortsluiting veroorzaken.

--- /collapse ---

+ Gebruik een **nieuw stuk geleidende draad** om het **output** gat van de tweede NeoPixel aan te sluiten op het **input** gat van de derde pixel. Ga op deze manier door totdat alle NeoPixels aan elkaar gekoppeld zijn langs hun **data** gaten, met een apart stuk draad tussen elk paar. De keten eindigt met de laatste NeoPixel: Je hecht niets aan zijn **output** gat.

![](images/pixelSewing3_136_800.png)

Vervolgens verbind je alle **negatieve** gaten in de keten, en vervolgens alle **positieve** gaten.

+ Naai met een lang stuk geleidende draad, ongeveer 50–100cm, een paar nauwe steken door het **-** gat van elke pixel, te beginnen met de eerste en eindigend met de laatste, en naai een rijgsteek tussen de NeoPixels.

**Opmerking**: Zorg ervoor dat de draad geen van de draden in de **data**-lijn raakt of kruist!

+ Verbind met nog een lang stuk geleidende draad alle **+** gaten van de NeoPixels op dezelfde manier als de **-** gaten.

+ Plaats ten slotte het Flora bord op het T-shirt \(zorg ervoor dat het **niet is aangesloten**!\).

+ Gebruik drie **afzonderlijke** stukken geleidende draad om het **\#6** gat van het bord te verbinden met het **input** gat van de eerste NeoPixel, het **GND** gat van het bord met het **sterke> gat van de eerste Neox-id** En het **VBATT** gat van het bord met het **+** gat van de eerste NeoPixel, waarbij een rijgsteek langs de stof wordt genaaid. Zorg ervoor dat geen van de draden elkaar raken.

+ Als je wilt, kun je een aantal van de ongebruikte pinnen van de Flora met wat gewone draad aan het T-shirt hechten om het beter op zijn plaats te houden.

![](images/stitchedCircuit.png)

+ Nu, het moment van de waarheid: Sluit je Flora aan.

Je zou al je NeoPixels moeten zien oplichten!

--- collapse ---
---
title: Er is iets niet goed
---

Als sommige van je NeoPixels niet oplichtten, raak dan niet in paniek. Enkele oorzaken kunnen zijn:

+ Een kortsluiting: Raken draden elkaar? Zit er iets van metaal op de stof of raakt het het circuit? Is de stof nat?

+ Losse verbindingen: De steken in elk gat moeten goed en strak zijn voor een veilige verbinding.

+ Juiste code geüpload: Heeft je code het juiste aantal NeoPixels gedefinieerd? Is het zonder fouten gecompileerd en geüpload?

--- /collapse --- 
