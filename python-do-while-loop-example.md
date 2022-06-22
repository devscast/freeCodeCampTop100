# Python Do While - Exemple de boucle

![img cover](https://www.freecodecamp.org/news/content/images/size/w2000/2021/08/pexels-pixabay-106155.jpg)

##### Les boucles sont une fonctionnalité utile et fréquemment utilisée dans tous les langages de programmation modernes.

Si vous souhaitez automatiser une tâche répétitive spécifique ou vous empêcher d'écrire du code répétitif dans vos programmes, l'utilisation d'une boucle est la meilleure option pour cela.

Les boucles sont un ensemble d'instructions qui s'exécutent de manière répétée jusqu'à ce qu'une condition soit remplie. Voyons comment les boucles fonctionnent en Python.

## Boucles en Python

Il existe deux types de boucles intégrées à Python :

+ les boucles ==for==
+ les boucles ==while==

Nous allons nous concentrer sur la façon dont vous pouvez créer une boucle ==while== en Python et sur son fonctionnement.

## Qu'est-ce qu'une boucle while en Python ?

La syntaxe générale d'une boucle ==while== en Python ressemble à ceci :

```` {python}
    while condition:
        execute this code in the loop's body
````

Une boucle while exécute un morceau de code tant qu'une condition est vraie. Elle continuera à exécuter l'ensemble des instructions de code souhaitées jusqu'à ce que cette condition ne soit plus vraie.

Une boucle while vérifie toujours la condition avant de s'exécuter.

Si la condition est ==vraie==, la boucle exécutera le code dans le corps de la boucle.

Par exemple, cette boucle s'exécute tant que le ==nombre== est inférieur à ==10== :

```` py
number = 0
while number < 10:
    print(f"Number is {number}!")
    number = number + 1
````

Résulat

```
Number is 0!
Number is 1!
Number is 2!
Number is 3!
Number is 4!
Number is 5!
Number is 6!
Number is 7!
Number is 8!
Number is 9!
```

Ici, la variable ==nombre== est initialement fixée à ==0==.

Avant l'exécution de tout code, Python vérifie la condition (==number < 10==). Elle est évaluée à True, donc l'instruction print est exécutée et ==Number is 0== ! est imprimé sur la console.

Le ==nombre== est ensuite incrémenté de 1. La condition est réévaluée et elle est à nouveau vraie, donc toute la procédure se répète jusqu'à ce que le ==nombre== soit égal à ==9==.

Cette fois, ==Nombre est 9 !== est imprimé et nombre est incrémenté, mais maintenant nombre est égal à 10 donc la condition n'est plus remplie et donc la boucle est terminée.

Il est possible que la boucle ==while== ne s'exécute jamais si la condition n'est pas remplie, comme dans cet exemple :

``` py
number = 50
while number < 10 :
    print(f"Number is {number}!")
```
Comme la condition est toujours False, les instructions du corps de la boucle ne s'exécutent pas.
## Ne créez pas de boucles infinies

Comme vous l'avez vu dans l'exemple ci-dessus, les boucles ==while== sont généralement accompagnées d'une variable dont la valeur change pendant toute la durée de la boucle. Et c'est elle qui détermine finalement le moment où la boucle se termine.

Si vous n'ajoutez pas cette ligne, vous créerez une boucle infinie.

Le ==nombr==e ne sera pas incrémenté et mis à jour. Il sera toujours fixé et restera à ==0== et donc la condition ==nombre < 10== sera toujours vraie. Cela signifie que la boucle continuera à tourner éternellement.

```` py
# don't run this
number = 0
while number < 10:
    print(f"Number is {number}!")
```

Résultat
```
Number is 0!
Number is 0!
Number is 0!
Number is 0!
Number is 0!
Number is 0!
Number is 0!
...
```

Il fonctionne à l'infini.

C'est la même chose que de faire ça :

```` py
#Ne pas exécuter ceci
while True :
    print("Je suis toujours vrai")
````
Que faire si vous vous trouvez dans une situation comme celle-ci ?

Appuyez sur ==CTRL + C== pour vous échapper et mettre fin à la boucle.

### Qu'est-ce qu'une boucle do while ?

La syntaxe générale d'une boucle ==do while== dans d'autres langages de programmation ressemble à ceci :
````py
do {
  instruction de bloc de boucle à exécuter ;
  }
while(condition) ;
````

Par exemple, une boucle do while en C ressemble à ceci :

``` C
#include <stdio.h>
 
int main(void)
 {
   int i = 10 ;
   do {
      printf("la valeur de i : %i\n", i) ;
      i++ ;
      }
  while( i < 20 ) ;
 }
```

Ce qui est unique dans les boucles do while, c'est le fait que le code dans le bloc de la boucle sera exécuté au moins une fois.

Le code de l'instruction s'exécute une fois, puis la condition n'est vérifiée qu'après l'exécution du code.

Le code est donc exécuté une fois, puis la condition est vérifiée.

Si la condition vérifiée est vraie, la boucle continue.

Il existe des cas où vous souhaitez que votre code s'exécute au moins une fois, et c'est là que les boucles do while sont utiles.

Par exemple, lorsque vous écrivez un programme qui prend en compte les entrées des utilisateurs, vous pouvez demander uniquement un nombre positif. Le code sera exécuté au moins une fois. Si le nombre que l'utilisateur soumet est négatif, la boucle continuera à fonctionner. S'il est positif, elle s'arrêtera.

Python n'a pas de fonctionnalité intégrée pour créer explicitement une boucle ==do while== comme d'autres langages. Mais il est possible d'émuler une boucle ==do while== en Python.

## Comment émuler une boucle do while en Python

Pour créer une boucle ==do while== en Python, vous devez modifier légèrement la boucle ==while== afin d'obtenir un comportement similaire à celui d'une boucle ==do while== dans d'autres langages.

Pour rappel, une boucle ==do while== s'exécute au moins une fois. Si la condition est remplie, elle s'exécute à nouveau.

La boucle ==while==, quant à elle, ne s'exécute pas au moins une fois et peut en fait ne jamais s'exécuter. Elle s'exécute quand et seulement quand la condition est remplie.

Disons donc que nous avons un exemple où nous voulons qu'une ligne de code soit exécutée au moins une fois.

```py
secret_word = "python"
counter = 0

while True:
    word = input("Enter the secret word: ").lower()
    counter = counter + 1
    if word == secret_word:
        break
    if word != secret_word and counter > 7: 
        break
```

Le code sera exécuté au moins une fois, en demandant l'entrée de l'utilisateur.

Il est toujours garanti de s'exécuter au moins une fois, avec ==True==, qui sinon crée une boucle infinie.

Si l'utilisateur saisit le mot secret correct, la boucle est terminée.

Si l'utilisateur saisit le mot secret erroné plus de 7 fois, la boucle s'arrête complètement.

L'instruction ==break== vous permet de contrôler le flux d'une boucle ==while== et de ne pas aboutir à une boucle infinie.

L'instruction ==break== met immédiatement fin à la boucle en cours et en sort.

Voici donc comment créer un effet similaire à celui d'une boucle ==do while== en Python.

La boucle s'exécute toujours au moins une fois. Elle continuera à tourner en boucle si une condition n'est pas remplie et se terminera lorsqu'une condition sera remplie.

# Conclusion

Vous savez maintenant comment créer une boucle ==do while== en Python.

Si vous souhaitez en savoir plus sur Python, vous pouvez regarder [la vidéo 12 Python Projects](https://www.youtube.com/watch?v=8ext9G7xspg&t=40s) sur la chaîne YouTube de freeCodeCamp. Vous aurez l'occasion de réaliser 12 projets et cette vidéo s'adresse aux débutants.

freeCodeCamp propose également une [certification Python](https://www.freecodecamp.org/learn/scientific-computing-with-python/) gratuite pour vous aider à acquérir une bonne compréhension et un aperçu complet des principes fondamentaux du langage.

Vous pourrez également créer cinq projets à la fin du cours pour mettre en pratique ce que vous avez appris.

Merci de votre lecture et bon apprentissage !

Dionysia Lemonaki

Learning something new everyday and writing about it


