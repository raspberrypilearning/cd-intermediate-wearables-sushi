## Couleur et lumière

Tu vas maintenant écrire ta propre **fonction**. Les fonctions organise ton code.

+ Au bas du croquis, clique **après** le `}` \(donc, en dehors de la fonction `loop`\) et appuie plusieurs fois sur <kbd>Retour</kbd>. Tape ensuite le code suivant :

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

Remarque : tout le code dans une **fonction** se place entre une paire d'**accolades** `{ }`.

+ Maintenant, change ton code `setup` pour qu'il ressemble à ceci :

``` 
    void setup() {
        // put your setup code here, to run once:
        strip.begin();
        strip.show();
        lightAll();
    }
```

La dernière ligne du code **appelle** la fonction que tu as effectuée. Cela signifie qu'il indique à la fonction de s'exécuter.

+ Vérifie et télécharge ton croquis dans le Flora. Tous les pixels sont-ils allumés en bleu ?

--- collapse ---
---
title: Comptage des pixels
---

Tu as peut-être compris que le premier nombre de la ligne `strip.setPixelColor(0, strip.Color(0, 0, 255));` décide quel pixel allumer.

As-tu remarqué que le premier pixel est `0` au lieu de `1` ? Donc, si tu as huit pixels, le dernier est le numéro `7`.

--- /collapse ---

+ Modifie la deuxième ligne de la fonction `lightAll` de :

```
    strip.setPixelColor(1, strip.Color(0, 0, 255));
```

en :

```
    strip.setPixelColor(1, strip.Color(255, 0, 0));
```

+ Vérifie et télécharge le code dans le Flora. Peux-tu repérer la différence ?

--- collapse ---
---
title: Comment les couleurs fonctionnent-elles dans le code ?
---

Sur un ordinateur, les couleurs sont créées en mélangeant les trois **couleurs primaires** : **rouge**, **vert** et **bleu**.

Tu utiliseras des nombres de `0` à `255` pour indiquer à l'ordinateur la quantité de chaque couleur à mélanger. Ainsi, le code `strip.Color(0, 0, 255)` donne du **bleu** car les valeurs du rouge et du vert sont toutes les deux à `0`.

+ Quelle couleur penses-tu que `strip.Color(0, 255, 0)` te donnera ? Essaie !

--- /collapse ---

Voici quelques autres couleurs à connaître :

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

+ Essaie d'expérimenter avec les nombres pour obtenir différentes nuances. Que penses-tu que tu obtiendras si tu définis une valeur de `0` pour les trois couleurs, `strip.Color(0, 0, 0)` ?

Vois-tu encore des étoiles ?! Ces NeoPixels sont vraiment LUMINEUX, n'est-ce pas !

+ Heureusement, si tu le souhaites, tu peux modifier leur luminosité avec l'instruction `strip.setBrightness(10);`. Ajoute-le à la fonction `setup` , entre les lignes `strip.begin();` et `strip.show();`. Tout comme pour les couleurs, le nombre peut être compris entre `0` et `255`.

--- collapse ---
---
title: Alimenter de nombreux NeoPixels
---

Tu constateras peut-être que les couleurs ne s'affichent pas correctement vers la fin de la chaîne. C'est parce que le circuit perd de la puissance en raison de **résistance** dans le fil.

+ Tu peux résoudre cela en cousant un fil supplémentaire le long des pistes **négatives** et **positives** de ton circuit.

--- /collapse ---
