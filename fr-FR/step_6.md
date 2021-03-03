## Lumières clignotantes

+ Crée la nouvelle fonction suivante après la première :

``` 
    void lightAllOneColour(uint32_t c) {
        strip.setPixelColor(0, c);
        strip.setPixelColor(1, c);
        strip.setPixelColor(2, c);
        strip.setPixelColor(3, c);
        strip.setPixelColor(4, c);
        strip.setPixelColor(5, c);
        strip.setPixelColor(6, c);
        strip.setPixelColor(7, c);
        strip.show();
    }
```

--- collapse ---
---
title: Que contiennent les parenthèses ?
---

Cette fonction prend un **paramètre** : c'est le bit entre les parenthèses. Ce sont des informations supplémentaires que tu donnes à la fonction lorsque tu l’appelles.

--- /collapse ---

+ Cette fois, tu écriras tes appels de fonction dans `loop` au lieu de `setup`. Clique à l'intérieur de la fonction `loop` et ajoute du code pour qu'il ressemble à ceci :

```
    void loop() {
        lightAllOneColour(strip.Color(0, 0, 255));
        delay(200);
        lightAllOneColour(strip.Color(0, 0, 0));
        delay(200);
    }
```

--- collapse ---
---
title: Fonctionnement du paramètre
---

Tu vois comment tu passes une couleur comme **paramètre** à ta fonction `lightAllOneColour` ? C'est la couleur qui est utilisée à la place de `c` sur chaque ligne à l'intérieur de cette fonction. Cela signifie que tu peux utiliser la même fonction pour rendre les NeoPixels de n'importe quelle couleur, et tu peux même tous les désactiver !

--- /collapse ---

+ Supprime la ligne `lightAll();` depuis l'intérieur de la fonction `setup`. Vérifie et télécharge le code.

--- collapse ---
---
title: À propos des fonctions setup et loop
---

Lorsque le Flora s'allume, il exécute d'abord tout le code de la fonction `setup` , puis il exécute la fonction `loop` encore et encore indéfiniment !

--- /collapse ---

+ À ton avis, que fait la fonction `delay` ? Essaie de mettre différentes valeurs pour son **paramètre**, par exemple `delay(50);` ou `delay(1000);`. N'oublie pas de vérifier et de télécharger le code pour tester tes modifications !

+ As-tu remarqué que la couleur `(0, 0, 0)` désactive les pixels ? Essaie d'exécuter le code suivant sur le Flora :

```
    void loop() {
        lightAllOneColour(strip.Color(255, 0, 255));
        delay(500);
        lightAllOneColour(strip.Color(0, 0, 0));
        delay(500);
        lightAllOneColour(strip.Color(255, 127, 0));
        delay(500);
        lightAllOneColour(strip.Color(0, 0, 0));
        delay(500);
    }
```

+ Maintenant, exécute le même code sans la couleur « off » :

```
    void loop() {
        lightAllOneColour(strip.Color(255, 0, 255));
        delay(500);
        lightAllOneColour(strip.Color(255, 127, 0));
        delay(500);
    }
```

+ Vois-tu la différence ?

+ Essaie de concevoir ta propre séquence en modifiant le code dans la fonction `loop` ! Tu peux ajouter autant de « delay » et d'appels à ta fonction `lightAllOneColour` que tu le souhaites. Expérimente avec des « delay » de plus en plus courts et des valeurs différentes pour le paramètre de couleur.

N'oublie pas que toute la séquence continuera à se répéter encore et encore si tu mets ton code dans la fonction `loop`. 
