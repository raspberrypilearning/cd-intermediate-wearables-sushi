## Animer !

+ Crée la nouvelle fonction suivante en bas de ton croquis :

``` 
    void animateOneColour(uint32_t c, uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, c);
            strip.show();
        }
    }
```

Peux-tu voir que cette fonction prend **deux** paramètres dans les parenthèses ? Plus tard, tu modifieras le code de la fonction pour qu'il utilise le second.

+ Supprime le code dans la fonction `loop` et ajoute un appel à ta nouvelle fonction :

```
    void loop() {
        animateOneColour(strip.Color(0, 0, 255), 100);
    }
```

Remarque comment tu passes entre parenthèses les deux paramètres de la fonction `animateOneColour` ? Même si la fonction n'utilise pas encore la seconde, mais le code ne se compilera pas si tu ne transmets pas de valeurs pour tous les paramètres lorsque tu appelles la fonction.

+ Vérifie et télécharge ton code. Que remarques-tu ?

Cette fois, tu n'as besoin que d'écrire **une ligne** de code qui appelle `strip.setPixelColor`et tous les pixels sont activés.

+ Dans ta nouvelle fonction, peux-tu voir qu'il existe une autre paire d'**accolades** avec du code entre les deux ? Cette paire appartient à quelque chose appelé une **boucle for** \(mais pas la fonction `loop` !\). Ça ressemble ça :

``` 
    for(uint16_t i=0; i<strip.numPixels(); i++) {

    }
```

--- collapse ---
---
title: Comment fonctionne le code ?
---

Le code ci-dessus vérifie le nombre de NeoPixels dans ta chaîne, puis exécute le code à l'intérieur des accolades autant de fois.

**Voici le bit intelligent :** la valeur de `i` commence par `0` et change de `1` chaque fois, donc à chaque fois la ligne `strip.setPixelColor(i, c);` s'exécute, il définit la couleur des **prochains** pixels !

--- /collapse ---

+ Il est temps de faire quelque chose avec ce deuxième paramètre ! Dans ta fonction `animateOneColour` , ajoute la ligne suivante sous la ligne `strip.show();` :

```
    delay(wait);
```

Assures-toi que la nouvelle ligne est **au-dessus de la** première `}`, afin qu'elle soit à l'intérieur de la boucle for. Ta fonction devrait ressembler à ceci maintenant :

``` 
    void animateOneColour(uint32_t c, uint8_t wait) {
        for(uint16_t i=0; i<strip.numPixels(); i++) {
            strip.setPixelColor(i, c);
            strip.show();
            delay(wait);
        }
    }
```

Au lieu d'utiliser un nombre particulier pour le `delay`, tu utilises le deuxième paramètre de ta fonction. Cela signifie que tu peux choisir une valeur différente pour le `delay` chaque fois que tu appelles la fonction.

+ Ajoute un autre appel à ta fonction dans `loop` pour activer et désactiver les NeoPixels :

    ```
        void loop() {
            animateOneColour(strip.Color(0, 0, 255), 100);
            animateOneColour(strip.Color(0, 0, 0), 100);
        }
    ```

+ Vérifie à nouveau ton code et télécharge le croquis dans le Flora. Maintenant, tu as une séquence animée cool !

Bien sûr, tu n'es pas obligé d'éteindre les NeoPixels. Pourquoi ne pas les faire s'illuminer de plusieurs couleurs l'une après l'autre ?

```
    void loop() {
        animateOneColour(strip.Color(255, 127, 0), 100);
        animateOneColour(strip.Color(255, 0, 255), 100);
        animateOneColour(strip.Color(0, 255, 255), 100);
    }
```

+ Ajoute autant de couleurs que tu le souhaites. Essaie également de passer des valeurs différentes autres que `100` pour le deuxième paramètre, et regarde ton animation accélérer ou ralentir !
