https://www.freecodecamp.org/news/python-for-loop-for-i-in-range-example/

# Boucle For Python - Exemple de For i in range

Les boucles sont l'une des principales structures de contrôle dans tout langage de programmation, et Python n'est pas différent.

Dans cet article, nous allons examiner quelques exemples d'utilisation de boucles `for` avec la fonction `range()` de Python.

## Boucles For en Python

Les boucles `for` répètent une partie du code pour un ensemble de valeurs.

Comme indiqué dans [la documentation de Python](https://docs.python.org/3/tutorial/controlflow.html#for-statements), les boucles `for` fonctionnent de manière légèrement différente de celle des langages tels que JavaScript ou C.

Une boucle `for` définit la variable iterator sur chaque valeur d'une liste, d'un tableau ou d'une chaîne de caractères et répète le code dans le corps de la boucle `for` pour chaque valeur de la variable iterator.

Dans l'exemple ci-dessous, nous utilisons une boucle `for` pour imprimer tous les chiffres de notre tableau.

```python
# Example for loop
for i in [1, 2, 3, 4]:
    print(i, end=", ") # prints: 1, 2, 3, 4,
```

Nous pouvons également inclure une logique plus complexe dans le corps d'une boucle `for`. Dans cet exemple, nous imprimons le résultat d'un petit calcul basé sur la valeur de notre variable iterator.


```python 
# More complex example
for i in [1, 3, 5, 7, 9]:
    x = i**2 - (i-1)*(i+1)
    print(x, end=", ") # prints 1, 1, 1, 1, 1, 
```

Lorsque les valeurs du tableau de notre boucle for sont séquentielles, nous pouvons utiliser la fonction `range()` de Python au lieu d'écrire le contenu de notre tableau.

## La fonction Range en Python

La fonction `range()` fournit une séquence d'entiers basée sur les arguments de la fonction. Vous trouverez des informations supplémentaires dans [la documentation Python](https://docs.python.org/3/library/stdtypes.html#range) sur la fonction `range()`.

```python
range(stop)
range(start, stop[, step])
```

L'argument `start` est la première valeur de l'intervalle. Si `range()` est appelé avec un seul argument, alors Python suppose que `start = 0`.

L'argument `stop` est la limite supérieure de l'intervalle. Il est important de comprendre que cette valeur supérieure n'est pas incluse dans l'intervalle.

Dans l'exemple ci-dessous, nous avons une plage commençant à la valeur par défaut de `0` et incluant les entiers inférieurs à `5`.

```python 
# Example with one argument
for i in range(5):
    print(i, end=", ") # prints: 0, 1, 2, 3, 4,
```

Dans notre prochain exemple, nous définissons `start = -1` et incluons à nouveau les entiers inférieurs à `5`.


```python
# Example with two arguments
for i in range(-1, 5):
    print(i, end=", ") # prints: -1, 0, 1, 2, 3, 4, 
```

La valeur optionnelle `step` du pas contrôle l'incrément entre les valeurs de la plage. Par défaut, pas `step= 1`.

Dans notre dernier exemple, nous utilisons l'intervalle des nombres entiers de `-1` à `5` et définissons le pas `step = 2`.

```python 
# Example with three arguments
for i in range(-1, 5, 2):
    print(i, end=", ") # prints: -1, 1, 3, 
```

## Résumé

Dans cet article, nous avons étudié les boucles `for` en Python et la fonction `range()`.

Les boucles `for` répètent un bloc de code pour toutes les valeurs d'une liste, d'un tableau, d'une chaîne ou d'un `range()`.

Nous pouvons utiliser la fonction `range()` pour simplifier l'écriture d'une boucle `for`. La valeur d'arrêt de `range()` doit être spécifiée, mais nous pouvons également modifier la valeur de `start` et le `step` entre les entiers dans `range()`.


