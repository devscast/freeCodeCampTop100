# How to find the square root of a number and calculate it by hand

![img cover](https://www.freecodecamp.org/news/content/images/size/w2000/2021/06/5f9c9cba740569d1a4ca33db.jpg)

## Parfois, dans des situations quotidiennes, nous pouvons être confrontés à la tâche de devoir calculer la racine carrée d'un nombre. Que faire si nous n'avons pas de calculatrice ou de smartphone à portée de main ? Pouvons-nous utiliser un bon vieux papier et un crayon pour le faire à la manière d'une division longue ?
 
Oui, nous le pouvons, et il existe plusieurs méthodes différentes. Certaines sont plus complexes que d'autres. Certaines fournissent des résultats plus précis.

Celle que je veux partager avec vous est l'une d'entre elles. Pour que cet article soit plus facile à lire, chaque étape est accompagnée d'illustrations.

## ÉTAPE 1 : Séparer les chiffres en paires 

![img step1Alt](https://www.freecodecamp.org/news/content/images/2020/01/step1Alt.png)

Pour commencer, organisons l'espace de travail. Nous allons diviser l'espace en trois parties. Ensuite, séparons les chiffres du nombre en paires en allant de droite à gauche.

Par exemple, le nombre 7 469,17 devient 74 69.  17. Ou dans le cas d'un nombre avec un nombre impair de chiffres, comme 19 036, nous commencerons par 1 90 36.

Dans notre cas, 2 025 devient 20 25.
## ÉTAPE 2 : Trouver le plus grand nombre entier

![img step2](https://www.freecodecamp.org/news/content/images/2020/01/step2.png)

L'étape suivante consiste à trouver le plus grand nombre entier (i) dont le carré est inférieur ou égal au nombre le plus à gauche.

Dans notre exemple actuel, le nombre le plus à gauche est 20. Puisque 4² = 16 <= 20 et 5² = 25 > 20, le nombre entier en question est 4. Déposons 4 dans le coin supérieur droit et 4² = 16 dans le coin inférieur droit.
## ÉTAPE 3 : Maintenant, soustrayez ce nombre entier 

![img step3](https://www.freecodecamp.org/news/content/images/2020/01/step3.png)

Maintenant, nous devons soustraire le carré de ce nombre entier (qui est égal à 16) du nombre le plus à gauche (qui est égal à 20). Le résultat est égal à 4 et nous allons l'écrire comme indiqué ci-dessus.
## ÉTAPE 4 : Passons à la paire suivante

![img step4](https://www.freecodecamp.org/news/content/images/2020/01/step4.png)

Ensuite, nous descendons la paire suivante dans notre nombre (qui est 25). Nous l'écrivons à côté de la valeur soustraite déjà présente (qui est 4).

Maintenant, multiplions le nombre dans le coin supérieur droit (qui est également 4) par 2. Le résultat est 8 et nous l'écrivons dans le coin inférieur droit suivi de _ x _ =.
## ÉTAPE 5 : Trouvez la bonne correspondance
![img step5](https://www.freecodecamp.org/news/content/images/2020/01/step5.png)

Il est temps de remplir chaque espace vide avec le même nombre entier (i). Il doit s'agir du plus grand nombre entier possible qui permet au produit d'être inférieur ou égal au nombre de gauche.

Par exemple, si nous choisissons le nombre 6, le premier nombre devient 86 (8 et 6) et nous devons également le multiplier par 6. Le résultat 516 est supérieur à 425, nous allons donc plus bas et essayons 5. Le chiffre 8 et le chiffre 5 nous donnent 85. 85 fois 5 donne 425, ce qui est exactement ce dont nous avons besoin.

Écrivez 5 à côté de 4 dans le coin supérieur droit. C'est le deuxième chiffre de la racine.
## ÉTAPE 6 : Soustrayez à nouveau
![img step6](https://www.freecodecamp.org/news/content/images/2020/01/step6.png)

Soustrayez le produit que nous avons calculé (qui est 425) du nombre actuel à gauche (également 425). Le résultat est zéro, ce qui signifie que la tâche est terminée.

Remarque : j'ai choisi exprès un carré parfait (2025 = 45 x 45). De cette façon, je pouvais montrer les règles de résolution des problèmes de racine carrée.

En réalité, les nombres sont composés de nombreux chiffres, y compris ceux qui suivent la virgule. Dans ce cas, nous répétons les étapes 4, 5 et 6 jusqu'à ce que nous obtenions la précision souhaitée.

L'exemple suivant explique ce que je veux dire.
## EXEMPLE : Nous creusons davantage...

Cette fois, le nombre est composé d'un nombre impair de chiffres, y compris ceux qui suivent la virgule.
![img EX1](https://www.freecodecamp.org/news/content/images/2020/01/EX1.png)

![img EX2](https://www.freecodecamp.org/news/content/images/2020/01/EX2.png)

![img EX3](https://www.freecodecamp.org/news/content/images/2020/01/EX3.png)

![img EX4](https://www.freecodecamp.org/news/content/images/2020/01/EX4.png)

![img EX5](https://www.freecodecamp.org/news/content/images/2020/01/EX5.png)

![img EX6](https://www.freecodecamp.org/news/content/images/2020/01/EX6.png)

![img EX7](https://www.freecodecamp.org/news/content/images/2020/01/EX7.png)

Comme nous l'avons vu dans cet exemple, le processus peut être répété plusieurs fois pour atteindre le niveau de précision souhaité.

### Auteur: Alexander Arobelidze 
#### Titre: La fascination pour le monde des mathématiques me rend un grand service dans mon parcours pour devenir un développeur accompli. Je suis enthousiaste à l'idée d'aider les autres à acquérir des ressources de haute qualité. 

