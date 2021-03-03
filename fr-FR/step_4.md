## Écrire ton propre code

+ Dans Arduino IDE, clique sur **Fichier** puis sur **Nouveau**. Tu obtiendras un **croquis** vierge qui ressemble à ceci :
```
    void setup() {
        // put your setup code here, to run once:

    }
    void loop() {
        // put your main code here, to run repeatedly:

    }
```

--- collapse ---
---
title: Commenter ton code
---

Toute ligne commençant par `//` est un **commentaire**. Les commentaires sont ignorés par l'ordinateur.

Ils sont utiles pour prendre des notes pour toi ou pour d'autres personnes qui veulent ton code !

--- /collapse ---

+ Va sur **croquis** , puis **Inclure une bibliothèque**, et sélectionne **Adafruit NeoPixel**. Tu devrais voir ce code s'ajouter en haut de ton croquis : `#include <Adafruit_NeoPixel.h>`.

+ Clique à la fin de la ligne et appuie plusieurs fois sur la touche <kbd>Retour</kbd> pour ajouter des lignes vides en dessous.

+ Sous la nouvelle ligne de code, tape ce qui suit : `#define PIXELS_PIN 6`

Avec ce code, tu définis la broche (identique à un trou ici, rappelle-toi) du Flora à utiliser pour **data** \(instructions\). Ainsi, la broche à laquelle tu connectes les trous **data** des NeoPixels est le numéro **6**.

+ En dessous, tape `#define NUM_PIXELS 8`. C'est le nombre de NeoPixels dont tu disposes. Si tu as un nombre différent de huit, tape ce nombre au lieu de `8`.

+ Enfin, en dessous, tape :

``` 
    Adafruit_NeoPixel strip = Adafruit_NeoPixel(NUM_PIXELS, PIXELS_PIN, NEO_GRB + NEO_KHZ800);
```

+ Dans la fonction `setup` , ajoute les deux lignes suivantes :

``` 
    void setup() {
        // put your setup code here, to run once:
        strip.begin();
        strip.show();
    }
```

--- collapse ---
---
title: Qu'est-ce que la fonction setup ?
---

Le code `void setup ()` définit la fonction `setup`. Il s'agit d'un bloc de code qui s'exécute lorsque le Flora est activé.

Tout le code entre les accolades `{` et `}` se trouve dans la fonction et sera donc exécuté lorsque le Flora sera activé.

--- /collapse ---

+ Après `strip.show();`, appuie sur <kbd>Retour</kbd> et tape ces deux lignes ci-dessous :

``` 
    strip.setPixelColor(0, strip.Color(0, 0, 255));
    strip.show();
```

+ Clique sur **Vérifier** pour compiler ton code et rechercher les erreurs. S'il y a des erreurs, tu devras corriger le code et le vérifier à nouveau. Habituellement, les messages d'erreur t'indiquent quelle ligne de code doit être corrigée. Vérifie que tu l'as tapé exactement comme indiqué !

+ Branche le Flora et exécute ton code ! Appuie sur le bouton **reset** du Flora, puis sur le bouton **Télécharger**. Quand c'est fait, que se passe-t-il ?

Tu devrais voir le premier NeoPixel s'allumer en bleu.

+ Faisons un autre ! **Au-dessus du** deuxième `show();`, tape deux autres lignes :

```
    strip.setPixelColor(1, strip.Color(0, 0, 255));
    strip.setPixelColor(2, strip.Color(0, 0, 255));
```

La fonction `setup` devrait ressembler à ceci maintenant :

``` 
    void setup() {
        // put your setup code here, to run once:
        strip.begin();
        strip.show();
        strip.setPixelColor(0, strip.Color(0, 0, 255));
        strip.setPixelColor(1, strip.Color(0, 0, 255));
        strip.setPixelColor(2, strip.Color(0, 0, 255));
        strip.show();
    }
```

Peux-tu déterminer ce que fait une partie de ce code ?

+ Vérifie et télécharge à nouveau ton code. Cette fois, tu devrais voir les trois premiers NeoPixels s'allumer en bleu.

+ Vois si tu peux ajouter plus de lignes de code pour que le reste des pixels s'allume également !

![](images/threeBlue.png)


