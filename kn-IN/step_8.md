## ಮಳೆಬಿಲ್ಲು ವಿನೋದ

+ ನಿಮ್ಮ ಸ್ಕ್ರಿಪ್ಟ್‌ನ ಕೊನೆಯಲ್ಲಿ ಈ ಕೆಳಗಿನ ಕೋಡ್ ಅನ್ನು ಸೇರಿಸಿ. ಚಿಂತಿಸಬೇಡಿ, ನೀವು ಇದೀಗ ಅದನ್ನು ಅರ್ಥಮಾಡಿಕೊಳ್ಳಬೇಕಾಗಿಲ್ಲ! ನೀವು ಮೊದಲು ಓಡಿಸಿದ ಉದಾಹರಣೆ ಸ್ಕೆಚ್‌ನಿಂದ ಇದನ್ನು ಎರವಲು ಪಡೆಯಲಾಗಿದೆ.


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

ಈ ಫಂಕ್ಷನ್ ನಿಮಗೆ `0` ಯಿಂದ `255` ವರೆಗೆ ಯಾವುದೇ ಸಂಖ್ಯೆ ಆಯ್ಕೆ ಮಾಡಲು ಅನುಮತಿಸುತ್ತದೆ, ಮತ್ತು ಅದು ನಿಮಗೆ ಒಂದು ಬಣ್ಣವನ್ನು ಮಿಶ್ರಮಾಡುತ್ತದೆ.

+ ಈಗ ಮತ್ತೊಂದು ಹೊಸ ಫಂಕ್ಷನ್ ಸೇರಿಸಿ. ಇದರಲ್ಲಿ ನೀವು **for loop** ಅನ್ನು ಗುರುತಿಸಬಹುದೇ ನೋಡಿ!

```
    void lightAllRainbow() {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels())) & 255));
            strip.show();
        }
    }
```

ಇಲ್ಲಿ ಸ್ವಲ್ಪ ಗಣಿತವಿದೆ! ಇಡೀ ಮಳೆಬಿಲ್ಲಿನಾದ್ಯಂತ ಉತ್ತಮ ಬಣ್ಣಗಳ ಆಯ್ಕೆಯನ್ನು ಸಮನಾಗಿ ತೆಗೆದುಕೊಳ್ಳಲು ಇದು ಇದೆ.

+ ಫಂಕ್ಷನ್ ಗೆ ಕರೆ ಮಾಡುವುದು ಮಾತ್ರ ಬಾಕಿ ಇದೆ. `loop` ಫಂಕ್ಷನ್ ಅನ್ನು ಅದರಲ್ಲಿ ಕೇವಲ ಈ ಕೋಡ್ ಸಾಲು ಮಾತ್ರ ಇರುವಂತೆ ಬದಲಿಸಿ. ನಂತರ ಬಣ್ಣಗಳ ಒಂದು ಸುಂದರ ಮಳೆಬಿಲ್ಲನ್ನು ನೋಡಲು ನಿಮ್ಮ ಸ್ಕೆಚ್ ಅನ್ನು ಪರಿಶೀಲಿಸಿ ಅಪ್‌ಲೋಡ್ ಮಾಡಿ.

```
    void loop() {
        lightAllRainbow();
    }
```

ಈ ಬಾರಿ ನೀವು ಯಾವುದೇ ನಿಯತಾಂಕಗಳನ್ನು ಕಳುಹಿಸುವ ಅಗತ್ಯವಿಲ್ಲ, ಏಕೆಂದರೆ ಹೊಸ ಫಂಕ್ಷನ್ ನಿಮಗಾಗಿ ಬಣ್ಣಗಳನ್ನು ತಾನೇ ತಿಳಿದುಕೊಳ್ಳುತ್ತದೆ!

+ ಒಂದು ವಿಳಂಬವನ್ನು ಸೇರಿಸಿದರೆ ಹೇಗೆ? ಮೇಲಿನದೇ ರೀತಿಯ ಒಂದು ಹೊಸ ಫಂಕ್ಷನ್ ಬರೆಯೋಣ, ಆದರೆ ಅದು ನಿಮ್ಮ ನಿಯೋಪಿಕ್ಸೆಲ್ ಗಳನ್ನೂ ಆ್ಯನಿಮೇಟ್ ಮಾಡುವಂತೆ ಲೂಪ್ ಗೆ ಒಂದು ವಿಳಂಬವನ್ನು ಸೇರಿಸಿಕೊಳ್ಳುತ್ತಾ:

```
    void animateRainbow(uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels())) & 255));
            strip.show();
            delay(wait);
        }
    }
```

+ `loop` ಫಂಕ್ಷನ್ ನಲ್ಲಿರುವ ಫಂಕ್ಷನ್ ಕರೆಯನ್ನು ಬದಲಾಯಿಸಿ ಮತ್ತು ನಿಮ್ಮ ಇನ್ನೊಂದು `animate` ಫಂಕ್ಷನ್ ಅನ್ನು ಕೂಡ ಕರೆಯುವಂತೆ ಒಂದು ಹೊಸ ಕೋಡ್ ಸಾಲನ್ನು ಸೇರಿಸಿ:

```
    void loop() {
        animateRainbow(100);
        animateOneColour(strip.Color(0, 0, 0), 100);
    }
```

ಫ್ಲೋರಾದಲ್ಲಿ ಇದನ್ನು ಪ್ರಯತ್ನಿಸಿ!

--- challenge ---

## ಸವಾಲು: ನಿಮ್ಮ ಸ್ವಂತ ಅನುಕ್ರಮಗಳನ್ನು ಮಾಡಲು ಪ್ರಯತ್ನಿಸಿ

+ `animateRainbow` ಫಂಕ್ಷನ್ ನ ಮತ್ತು ನಿಮ್ಮ ಇತರ ಫಂಕ್ಷನ್ ಗಳ ಬೇರೆಬೇರೆ ಕರೆಗಳನ್ನು ಒಟ್ಟುಮಾಡಲು ಒಂದು ಪ್ರಯತ್ನ ಮಾಡಿ. ನಿಮ್ಮ ಕಲ್ಪನೆಯೇ ಮಿತಿ!

+ ನೀವು ಬಣ್ಣಗಳು, ಫಾರ್ ಲೂಪ್ ಗಳು, ಮತ್ತು ವಿಳಂಬಗಳಿಂದ ಕಲಿತ ತಂತ್ರಗಳನ್ನು ಬಳಸಿಕೊಂಡು ನೀವು ಬಹಳಷ್ಟು ಖುಷಿಕರ ಕೆಲಸಗಳನ್ನು ಮಾಡಬಹುದು. ನೀವು ಇನ್ನೂ ಕೆಲವು ಉದಾಹರಣೆಗಳನ್ನು ನೋಡಬೇಕೆಂದಿದ್ದರೆ, ನೀವು ನಿಯೋಪಿಕ್ಸೆಲ್ ಗಳನ್ನು ಪರೀಕ್ಷಿಸಲು ಬಳಸಿದ **strandtest** ಸ್ಕೆಚ್ ಅನ್ನು ಪರಿಶೀಲಿಸಿ.

--- /challenge ---

--- collapse ---
---
title: ಕೊಂಡೊಯ್ಯಬಹುದಾದ ಶಕ್ತಿ
---

ನಿಮ್ಮ ಪ್ರಾಜೆಕ್ಟ್ ಅನ್ನು ಧರಿಸಲು ನೀವು ಯೋಜಿಸುತ್ತಿದ್ದರೆ, ಬ್ಯಾಟರಿ ಶಕ್ತಿಯನ್ನು ಬಳಸಿಕೊಂಡು ಅದನ್ನು ಹೆಚ್ಚು ಪೋರ್ಟಬಲ್ (ಕೊಂಡೊಯ್ಯಬಹುದಾದ) ಮಾಡಲು ನೀವು ಬಯಸುತ್ತೀರಿ.

+ ಫ್ಲೋರಾಕ್ಕಾಗಿ, 3 × ಎಎ ಅಥವಾ 3 × ಎಎಎ ಬ್ಯಾಟರಿ ಪ್ಯಾಕ್ ಉತ್ತಮವಾಗಿ ಕಾರ್ಯನಿರ್ವಹಿಸುತ್ತದೆ. ಹೆಚ್ಚಿನ ಮಾಹಿತಿಗಾಗಿ [dojo.soy/wear2-flora-power](http://dojo.soy/wear2-flora-power){:target="_blank"} ನೋಡಿ.

+ ನೀವು ಬೇರೆ ಬೋರ್ಡ್ ಬಳಸುತ್ತಿದ್ದರೆ, ಅದು ಹೊಂದಿರುವ ವಿದ್ಯುತ್ ಅವಶ್ಯಕತೆಗಳನ್ನು ನೀವು ಮರುಪರಿಶೀಲಿಸಬೇಕು.

--- /collapse ---
