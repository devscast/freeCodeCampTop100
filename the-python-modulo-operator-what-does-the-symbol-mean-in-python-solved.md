https://www.freecodecamp.org/news/the-python-modulo-operator-what-does-the-symbol-mean-in-python-solved/

# L'opérateur modulo de Python - Que signifie le symbole % en Python ?

![](https://www.freecodecamp.org/news/content/images/size/w2000/2020/01/python-modulo-image.jpg)

Lorsque vous voyez le symbole %, vous pouvez penser "pourcentage". Mais en Python, ainsi que dans la plupart des autres langages de programmation, il a une signification différente.

Le symbole `%` en Python est appelé l'opérateur modulo. Il renvoie le reste de la division de l'opérande de gauche par l'opérande de droite. Il est utilisé pour obtenir le reste d'un problème de division.

L'opérateur modulo est considéré comme une opération arithmétique, au même titre que `+`, `-`, `/`, `*`, `**`, `//`.

La syntaxe de base est la suivante :

```python
a % b
```

Dans l'exemple précédent, `a` est divisé par `b`, et le reste est renvoyé. Voyons un exemple avec des chiffres.

```python
7 % 2
```

Le résultat de l'exemple précédent est un. Deux va dans sept trois fois et il reste un.

Le diagramme ci-dessous donne une représentation visuelle de `7/2` et `7%2` (le "R" signifie "reste"). Le logo unique sur le côté droit (avec la flèche verte pointant vers lui) est le reste du problème de la division. C'est également la réponse à `7%2`

![](https://www.freecodecamp.org/news/content/images/2019/09/image-196.png)

Voici un autre exemple :

```python
3 % 4
```

Cela donnera **trois**. Quatre ne se transforme jamais en trois et il reste donc le **trois** initial. Le diagramme ci-dessous montre ce qui se passe. N'oubliez pas que l'opérateur modulo renvoie le reste après avoir effectué la division. Le reste est trois.

![](https://www.freecodecamp.org/news/content/images/2019/09/image-197.png)

## Exemple d'utilisation de l'opérateur modulo

Une utilisation courante de l'opérateur modulo consiste à trouver les nombres pairs ou impairs. Le code ci-dessous utilise l'opérateur modulo pour imprimer tous les nombres impairs compris entre 0 et 10.

```python
for number in range(1, 10):
    if(number % 2 != 0):
        print(number)
```

Le résultat :

```
1
3
5
7
9
```