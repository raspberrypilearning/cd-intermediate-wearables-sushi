## एनिमेट! (Animate)

+ अपने स्केच के नीचे निम्नलिखित नया फंक्शन बनाएँ:

``` 
    void animateOneColour(uint32_t c, uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, c);
            strip.show();
        }
    }
```

क्या आप देख सकते हैं कि यह फ़ंक्शन **दो** बार गोल ब्रेसिज़ का पैरामीटर करता है? बाद में, आप फ़ंक्शन के कोड को बदल देंगे ताकि यह दूसरे का उपयोग करे।

+ `loop` फ़ंक्शन से कोड हटाएं और अपने नए फ़ंक्शन के लिए कॉल में जोड़ें:

```
    void loop() {
        animateOneColour(strip.Color(0, 0, 255), 100);
    }
```

ध्यान दें कि आप `animateOneColour` से कैसे गुजर रहे हैं कोष्ठक में दो पैरामीटर कार्य करते हैं? भले ही फ़ंक्शन अभी तक दूसरे का उपयोग नहीं करता है, लेकिन जब आप फ़ंक्शन को कॉल करते हैं, तो आप सभी मापदंडों के मानों में पास नहीं होने पर कोड संकलित नहीं करेंगे।

+ अपना कोड एक बार और सत्यापित करें और अपलोड करें। तुमने क्या देखा?

इस बार आपको केवल **एक पंक्ति** कोड की लिखने की आवश्यकता थी जो `strip.setPixelColor` कॉल करता है और सभी पिक्सेल चालू हो जाते है।

+ अपने नए फ़ंक्शन के अंदर, क्या आप देख सकते हैं कि **घुंघराले ब्रेसिज़ की एक और जोड़ी है** बीच में कुछ कोड के साथ? यह जोड़ी **for loop** नामक से संबंधित है (लेकिन `loop` फंक्शन नहीं है!)। यह इस तरह दिखता है:

``` 
    for(uint16_t i=0; i<strip.numPixels(); i++) {

    }
```

--- collapse ---
---
title: यह कैसे काम करता है?
---

उपरोक्त कोड यह जांचता है कि आपकी श्रृंखला में कितने NeoPixels हैं और फिर कई बार घुंघराले ब्रेस (curly braces) के अंदर कोड चलाता है।

**चतुराई वाली बात यहाँ है:** `i` का मूल्य शुरू `0` से होता है और हर बार `1` से बढ़ता है, तो हमेशा जब ये लाइन `strip.setPixelColor(i, c);` रन करता है तो वह पिक्सेल का नया या **next** रंग सेट करता है!

--- /collapse ---

+ उस दूसरे पैरामीटर के साथ कुछ करने का समय! अपने `animateOneColour` फंक्शन, `strip.show();` लाइन के नीचे निम्नलिखित पंक्ति जोड़ें:

```
    delay(wait);
```

सुनिश्चित करें कि नई लाइन पहले `}` के **ऊपर** है, ताकि यह लूप के अंदर हो। आपका कोड इस प्रकार दिखना चाहिए:

``` 
    void animateOneColour(uint32_t c, uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, c);
            strip.show();
            delay(wait);
        }
    }
```

`देरी` (delay) के लिए एक विशेष संख्या का उपयोग करने के बजाय, आप अपने फ़ंक्शन के दूसरे पैरामीटर का उपयोग कर रहे हैं। इसका मतलब है कि आप `delay` के लिए हर बार एक अलग मान चुन सकते हैं जब आप फ़ंक्शन को कॉल करते हैं।

+ `लूप` (loop) के अंदर अपने फ़ंक्शन में एक और कॉल जोड़ें ताकि NeoPixels बंद और शुरू साथ हो पाएँ:

    ```
        void loop() {
            animateOneColour(strip.Color(0, 0, 255), 100);
            animateOneColour(strip.Color(0, 0, 0), 100);
        }
    ```

+ अपने कोड को फिर से सत्यापित करें और स्केच को फ्लोरा पर अपलोड करें। अब आपके पास एक शांत एनिमेटेड अनुक्रम (animated sequence) है!

बेशक, आपको NeoPixels को बंद करने की आवश्यकता नहीं है। कैसा लगेगा जब हम उन सभी को एक के बाद एक रंगों का एक गुच्छा में प्रकाश करेंगे?

```
    void loop() {
        animateOneColour(strip.Color(255, 127, 0), 100);
        animateOneColour(strip.Color(255, 0, 255), 100);
        animateOneColour(strip.Color(0, 255, 255), 100);
    }
```

+ आप जितने चाहें उतने रंग जोड़ें। `100` के अलावा अन्य मूल्यों में पास होने का प्रयास करें दूसरे पैरामीटर के लिए भी, और अपने एनीमेशन को गति या धीमा देखें!
