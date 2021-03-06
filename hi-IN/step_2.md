## अपने LEDs का परीक्षण करें

शुरू करने से पहले, अपने प्रत्येक NeoPixels का परीक्षण करना एक अच्छा विचार है।

+ Arduino IDE खोलें। सुनिश्चित करें कि सही उपकरण **Tools** मेन्यू में चुना गया है । मैं फ्लोरा का उपयोग कर रहा हूं, इसलिए मेरे लिए यह **Adafruit Flora** है।

+ **File** मेन्यू पर जाएं, **Examples** चुने, फिर खोजें **Adafruit NeoPixel** \ (यह बहुत नीचे हो सकता है!) और **strandtest** चुनें ।

एक कोड फ़ाइल खुल जाएगी। एक कोड फ़ाइल को **sketch** कहा जाता है Arduino IDE में।

+ ये कोड के लाइन को ऊपर कि तरफ खोजें:

```
  Adafruit_NeoPixel strip = Adafruit_NeoPixel(60, PIN, NEO_GRB + NEO_KHZ800);
```

+ पहली संख्या को `1` में बदलें । आपका कोड इस प्रकार दिखना चाहिए:

  ```
    Adafruit_NeoPixel strip = Adafruit_NeoPixel(1, PIN, NEO_GRB + NEO_KHZ800);
  ```

+ **File** पर क्लिक करें और फिर **Save As...** दबाएं । अपने स्केच (sketch) के लिए एक नाम लिखें और **Save** पर क्लिक करें ।

+ अपने स्केच के शीर्ष पर, **verify** करने कि लिए टिक (चेक मार्क) आइकन पर क्लिक करें। खिड़की के नीचे आपको "Done Compiling" शब्द दिखना चाहिए जिसका अर्थ है कोड **compiled** सफलतापूर्वक (अगर न हुआ हो तो, आपको गलती दिखेगी I इन्हें ठीक करने के लिए, आपको कुछ डीबगिंग (debugging) करने और अपना कोड बदलने की आवश्यकता होगी!)।

![](images/verifyIcon.png)

अपलोड करने के लिए तैयार!

+ अपने फ्लोरा में प्लग करें। फ्लोरा बटन पर **reset** दबाएं और फिर **सीधे**, जबकि लाल बत्ती स्पंदित हो रही है, टिक आइकन / चेक मार्क के बगल में तीर आइकन पर क्लिक करें ताकि कोड बोर्ड पर **upload** होजाये ।

+ आपको लाल बत्ती चमकती दिखनी चाहिए, उसके बाद बोर्ड पर दो नारंगी रोशनी दिखाई देगी। जब यह समाप्त हो जाए, तो आपको "Done uploading" शब्द दिखने चाहिए, अपने स्केच (sketch) के नीचे।

![](images/upload3_120_800.png)

--- collapse ---
---
title: अपलोड करने में समस्याएँ
---

पहले तो यह अपलोड करने के लिए काम करने के लिए थोड़ा मुश्किल हो सकता है। सुनिश्चित करें कि सही बोर्ड का चयन किया गया है और आपके पास एक काम करने वाला यूएसबी केबल है जो दोनों सिरों पर ठीक से प्लग किया गया है। उसके बाद, यह सब समय के बारे में है! आप धीरे धीरे सीख जाएंगे I

--- /collapse ---

+ अपने कंप्यूटर से Flora को अनप्लग करें (आप बैटरी पैक का उपयोग करते समय इसे बंद करने के लिए फ्लोरा पर पावर स्विच का उपयोग कर सकते हैं, लेकिन जब बोर्ड USB के माध्यम से कंप्यूटर में प्लग किया जाता है) तो यह काम नहीं करता है।

**अन्य घटकों को जोड़ने या डिस्कनेक्ट करने से पहले बोर्ड को हमेशा अनप्लग या स्विच करना महत्वपूर्ण है ताकि आप उन्हें नुकसान न पहुंचाएं!**

+ बोर्ड के **GND** में तीन मगरमच्छ क्लिप संलग्न करें, **#6**, और **VBATT** पिंस।

![](images/crocsFlora.png)

+ एक NeoPixel लें और बोर्ड के **GND** तार को कनेक्ट करें इसके **-** पिन से। बोर्ड के **#6** पिन कनेक्ट करें **data in** में पिन करें: यह एक तीर है जिसकी ओर इंगित करते हुए **in towards** केंद्र में एलईडी की ओर। अंत में, बोर्ड के **VBATT** को कनेक्ट करें **+** पिन में।

![](images/crocsPixel.png)

+ तैयार? Flora में एक बार फिर से प्लग करें और अपने LED को एक बहुरंगी अनुक्रम को रोशन करने और चमकाने के लिए देखें!

+ अपने NeoPixels का परिक्षण एक एक करके Flora में जोड़कर करिये, ठीक वैसे ही जैसे आपने यह पहला वाला किया है I याद रखें **फ्लोरा को अनप्लग करें** किसी भी तार को जोड़ने या डिस्कनेक्ट करने से पहले!

+ एक बार जब आप NeoPixels का परीक्षण कर लेते हैं, तो आपके द्वारा उपयोग किए जा रहे NeoPixels की कुल संख्या के लिए कोड को फिर से बदल दें। मेरा आठ (8) है:

```
  Adafruit_NeoPixel strip = Adafruit_NeoPixel(8, PIN, NEO_GRB + NEO_KHZ800);
```

+ **Verify** पर क्लिक करें और फिर **upload** करें Flora पर नया कोड। अगला आप अपना NeoPixel सर्किट बनाने जा रहे हैं!
