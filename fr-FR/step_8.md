## Arc-en-ciel amusant

+ Ajoute la nouvelle fonction suivante à la fin de ton croquis. Ne t’inquiète pas, tu n'as pas à le comprendre tout de suite ! Il est emprunté à l'exemple de croquis que tu as exécuté plus tôt.


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

Cette fonction te permet de choisir n'importe quel nombre de `0` à `255`, et elle mélange une couleur pour toi.

+ Maintenant, ajoute une autre nouvelle fonction. Vois si tu peux y repérer la **boucle for** !

```
    void lightAllRainbow() {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels())) & 255));
            strip.show();
        }
    }
```

Il va falloir un peu calculer ! Il est là pour choisir une belle sélection de couleurs uniformément dans tout l'arc-en-ciel.

+ Il ne reste plus qu'à appeler la fonction. Modifie la fonction `loop` pour qu'elle contienne uniquement cette ligne de code. Ensuite, vérifie et télécharge ton croquis pour voir un bel arc-en-ciel de couleurs.

```
    void loop() {
        lightAllRainbow();
    }
```

Tu n'as pas besoin de passer de paramètres cette fois, car la nouvelle fonction détermine les couleurs pour toi !

+ Que dirais-tu d'ajouter un délai ? Écrivons une nouvelle fonction similaire à celle ci-dessus, mais avec un délai ajouté à la boucle pour qu'elle anime tes NeoPixels :

```
    void animateRainbow(uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, Wheel(((i * 256 / strip.numPixels())) & 255));
            strip.show();
            delay(wait);
        }
    }
```

+ Modifie l'appel de fonction dans la fonction `loop` et ajoute une deuxième ligne de code pour appeler également ton autre fonction `animate` :

```
    void loop() {
        animateRainbow(100);
        animateOneColour(strip.Color(0, 0, 0), 100);
    }
```

Essaie-le sur le Flora !

--- challenge ---

## Défi : essaie de créer tes propres séquences

+ Essaie de combiner différents appels à la fonction `animateRainbow` et à tes autres fonctions. La limite, c'est ton imagination !

+ Tu peux faire beaucoup de choses sympas en utilisant les astuces que tu as apprises avec les couleurs, les boucles for et les « delay ». Si tu souhaites voir plus d'exemples, consulte le croquis **strandtest** que tu as utilisé pour tester les NeoPixels.

--- /challenge ---

--- collapse ---
---
title: Alimentation portable
---

Si tu prévois de porter ton projet, tu voudrais probablement le rendre plus portable en utilisant une pile.

+ Pour le Flora, un bloc de piles 3 × AA ou 3 × AAA fera très bien l'affaire. Va voir sur [dojo.soy/wear2-flora-power](http://dojo.soy/wear2-flora-power){:target="_blank"} pour plus d'informations.

+ Si tu utilises une carte différente, tu dois revérifier les exigences d'alimentation dont elle dispose.

--- /collapse ---


***
Ce projet a été traduit par des bénévoles:

Jonathan Vannieuwkerke

Michel Arnols

Grâce aux bénévoles, nous pouvons donner aux gens du monde entier la chance d'apprendre dans leur propre langue. Vous pouvez nous aider à atteindre plus de personnes en vous portant volontaire pour la traduction - plus d'informations sur [rpf.io/translate](https://rpf.io/translate).