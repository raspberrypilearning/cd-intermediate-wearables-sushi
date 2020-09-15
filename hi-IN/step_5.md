## रंग और रोशनी

आप अभी अपना स्वयं का **फ़ंक्शन** लिखने जा रहे हैं। फ़ंक्शंस आपके कोड को व्यवस्थित रखते हैं।

+ स्केच के नीचे, **after** क्लिक करें जो इन `}` \ (इसलिए, `loop` के बाहर फ़ंक्शन \) और <kbd>Return</kbd> दबाएं दो तीन बार। निम्नलिखित कोड को टाइप करें:

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

नोट: सभी कोड **फ़ंक्शन** में **curly braces** घुंघराले ब्रैकेट्स की एक जोड़ी के बीच में जाता है `{ }` ।

+ अब अपना `सेटअप` कोड बदलें ताकि यह इस तरह दिखे:

``` 
    void setup() {
        // put your setup code here, to run once:
        strip.begin();
        strip.show();
        lightAll();
    }
```

आपके कोड की अंतिम पंक्ति या लाइन आपके बनाये हुए फंक्शन को **बुलाती** है I इसका मतलब है कि यह फ़ंक्शन को चलने के लिए कहता है।

+ अपने स्केच को फ़्लोरा में सत्यापित (verify) करें और अपलोड (upload) करें। क्या सभी पिक्सेल नीले रंग में जल रहे हैं?

--- collapse ---
---
title: पिक्सल की गिनती करना
---

आपको पता चल गया होगा कि लाइन में पहला नंबर `strip.setPixelColor(0, strip.Color(0, 0, 255));` कौन सा पिक्सेल पहले जलता हैं वो तय करता है।

क्या आपने देखा है कि पहला पिक्सेल `0 ` है `1` के बजाय? इसलिए यदि आपके पास आठ पिक्सेल हैं, तो अंतिम संख्या `7` होगी।

--- /collapse ---

+ `lightAll` की दूसरी पंक्ति यहाँ से बदलें:

```
    strip.setPixelColor(1, strip.Color(0, 0, 255));
```

ये करें:

```
    strip.setPixelColor(1, strip.Color(255, 0, 0));
```

+ अपने स्केच को फ़्लोरा में सत्यापित करें और अपलोड करें। क्या तुम अंतर बता सकते हो?

--- collapse ---
---
title: कोड में रंग कैसे काम करते हैं?
---

कंप्यूटर पर, तीन **प्राथमिक रंगों** को मिलाकर रंग बनाए जाते हैं:**लाल**, **हरा**, और **नीला** ।

आप `0` से `255` संख्याओं का उपयोग कर कंप्यूटर को यह बताने के लिए कि प्रत्येक रंग को कितना मिश्रण करना है। तो कोड `strip.Color(0, 0, 255)` बनाता है **नीला** क्योंकि लाल और हरे रंग का मूल्य दोनों `0` हैं।

+ आपको क्या रंग लगता है `strip.Color(0, 255, 0)` देगा? इसे आज़माएँ!

--- /collapse ---

यहाँ कुछ और रंग दिए गए हैं जिन्हें जानना अच्छा है:

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

+ विभिन्न रंगों को प्राप्त करने के लिए संख्याओं के साथ प्रयोग करने का प्रयास करें। आपको क्या लगता है अगर हम तीनों रंगों के लिए यदि `0`, `strip.Color(0, 0, 0)` तो हमे क्या मिलेगा?

क्या आप अभी तक तारे देख रहे हैं?! वो NeoPixels ऊज्ज्वल है ना!

+ सौभाग्य से, यदि आप चाहते हैं, तो आप निर्देश के साथ उनकी चमक को बदल सकते हैं ` strip.setBrightness(10); ` । इसे ` setup ` फ़ंक्शन में जोड़ें, लाइनों के बीच में ` strip.begin(); ` और ` strip.show();`। रंगों की तरह, संख्या ` 0 ` से ` 255 ` कुछ भी हो सकती है को ।

--- collapse ---
---
title: NeoPixels की बहुत सारी शक्ति
---

आप पा सकते हैं कि श्रृंखला के अंत की ओर रंग ठीक से दिखाई नहीं दे रहे हैं। ऐसा इसलिए है क्योंकि सर्किट **प्रतिरोध** (resistence) के कारण शक्ति खो रहा है।

+ आप दोनों के साथ एक अतिरिक्त धागा सिलाई करके इसे सुलझा सकते हैं **negative** और **positive** अपने सर्किट में।

--- /collapse ---
