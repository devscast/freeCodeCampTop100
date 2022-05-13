https://www.freecodecamp.org/news/list-index-out-of-range-python-error-message-solved/

# Index de la liste hors de la plage - Résolution d'un message d'erreur Python


Dans cet article, vous verrez quelques-unes des raisons qui provoquent l'erreur Python `list index out of range`.

En plus de savoir pourquoi cette erreur se produit en premier lieu, vous apprendrez également quelques moyens de l'éviter.

C'est parti !


## Comment créer une liste en Python

Pour créer un objet liste en Python, vous devez :

- Donner un nom à la liste,
- utiliser l'opérateur d'affectation, `=`,
- et inclure 0 ou plusieurs éléments de liste entre crochets,`[]`. Chaque élément de liste doit être séparé par une virgule.

Par exemple, pour créer une liste de noms, vous devez procéder comme suit :

```
names = ["Kelly", "Nelly", "Jimmy", "Lenny"]
```

Le code ci-dessus a créé une liste appelée names qui a quatre valeurs : `Kelly, Nelly, Jimmy, Lenny`.

## Comment vérifier la longueur d'une liste en Python ?

Pour vérifier la longueur d'une liste en Python, utilisez la méthode `len()` intégrée à Python.

`len()` renvoie un nombre entier, qui correspond au nombre d'éléments stockés dans la liste.


```py
names = ["Kelly", "Nelly", "Jimmy", "Lenny"]

#create a variable called name_length to store the length of the list
name_length = len(names)

#print value of variable to the console
print(name_length)

#output
#4
```

Il y a quatre éléments stockés dans la liste, la longueur de la liste sera donc de quatre.

## Comment accéder aux éléments individuels d'une liste en Python ?

Chaque élément d'une liste possède son propre *numéro d'index*.

L'indexation en Python, et dans la plupart des langages de programmation modernes, commence à 0.

Cela signifie que le premier élément d'une liste a un indice de 0, le deuxième élément un indice de 1, et ainsi de suite.

Vous pouvez utiliser le numéro d'index pour accéder à l'élément individuel.

Pour accéder à un élément d'une liste à l'aide de son numéro d'index, écrivez d'abord le nom de la liste. Puis, à l'intérieur des crochets, incluez l'indice qui correspond au numéro d'index de l'élément.

En reprenant l'exemple précédent, voici comment accéder à chaque élément de la liste à l'aide de son numéro d'index :


```py
names = ["Kelly", "Nelly", "Jimmy", "Lenny"]

names[0] # Kelly
names[1] # Nelly
names[2] # Jimmy
names[3] # Lenny
```

Vous pouvez également utiliser l'indexation négative pour accéder aux éléments des listes en Python.

Pour accéder au dernier élément, vous utilisez la valeur d'indexation de -1. Pour accéder à l'avant-dernier élément, vous utilisez la valeur d'indexation de -2.

Voici comment accéder à chaque élément d'une liste en utilisant l'indexation négative :


```py
names = ["Kelly", "Nelly", "Jimmy", "Lenny"]

names[-4] # Kelly
names[-3]# Nelly
names[-2] # Jimmy
names[-1] # Lenny
```

## Pourquoi l'erreur `Indexerror : list index out of range` se produit-elle en Python ?

### Utilisation d'un numéro d'index hors de la plage de la liste

Vous obtenez l'erreur `Indexerror : list index out of range` lorsque vous essayez d'accéder à un élément en utilisant une valeur qui est hors de la plage d'index de la liste et qui n'existe pas.

C'est assez fréquent lorsque vous essayez d'accéder au dernier élément d'une liste, ou au premier si vous utilisez une indexation négative.

Reprenons la liste que nous avons utilisée jusqu'à présent.

```py
names = ["Kelly", "Nelly", "Jimmy", "Lenny"]
```

Supposons que je veuille accéder au dernier élément, "Lenny", et que j'essaie de le faire en utilisant le code suivant :


```py
print(names[4])

#output

#Traceback (most recent call last):
#  File "/Users/dionysialemonaki/python_articles/demo.py", line 3, in <module>
#    print(names[4])
#IndexError: list index out of range
```


En général, la plage d'index d'une liste est comprise entre `0 et n-1`, `n` étant le nombre total de valeurs dans la liste.

Le nombre total de valeurs de la liste ci-dessus étant de `4`, l'intervalle d'indexation est de `0 à 3`.

Essayons maintenant d'accéder à un élément en utilisant l'indexation négative.

Disons que je veux accéder au premier élément de la liste, "Kelly", en utilisant l'indexation négative.


```py
names = ["Kelly", "Nelly", "Jimmy", "Lenny"]

print(names[-5])

#output

#Traceback (most recent call last):
#  File "/Users/dionysialemonaki/python_articles/demo.py", line 3, in <module>
#    print(names[-5])
#IndexError: list index out of range
```

Lorsqu'on utilise l'indexation négative, la plage d'indexation d'une liste est comprise entre `-1 et -n`, où `-n` est le nombre total d'éléments contenus dans la liste.

Si le nombre total d'éléments de la liste est de `4`, la plage d'indexation est de `-1 à -4`.

### Utilisation d'une valeur incorrecte dans la fonction `range()` d'une boucle for Python

Vous obtenez l'erreur Indexerror : list index out of range lorsque vous itérez dans une liste et essayez d'accéder à un élément qui n'existe pas.

Un cas courant où cela peut se produire est celui où vous utilisez le mauvais entier dans la fonction `range()` de Python.

La fonction `range()` prend généralement un nombre entier, qui indique où le comptage s'arrête.

Par exemple, `range(5)` indique que le comptage commencera à `0` et se terminera à `4`.

Ainsi, par défaut, le comptage commence à la position `0`, est incrémenté de `1` à chaque fois, et le nombre va jusqu'à - mais n'inclut pas - la position où le comptage s'arrêtera.

Prenons l'exemple suivant :


```py
names = ["Kelly", "Nelly", "Jimmy", "Lenny"]

for name in range(5):
    print(names[name])
    
#output

#Kelly
#Nelly
#Jimmy
#Lenny
#Traceback (most recent call last):
#  File "/Users/dionysialemonaki/python_articles/demo.py", line 7, in <module>
#   print(names[name])
#IndexError: list index out of range
```

Ici, la liste des `name` a quatre valeurs.

Je voulais boucler la liste et imprimer chaque valeur.

Lorsque j'ai utilisé `range(5)`, j'ai demandé à l'interpréteur Python d'imprimer les valeurs qui se trouvent aux positions `0 à 4`.

Cependant, il n'y a pas d'élément en position `4`.

Vous pouvez le constater en imprimant d'abord le numéro de la position, puis la valeur qui s'y trouve.

```
#0
#Kelly
#1
#Nelly
#2
#Jimmy
#3
#Lenny
#4
#Traceback (most recent call last):
#  File "/Users/dionysialemonaki/python_articles/demo.py", line 8, in <module>
#    print(names[name])
#IndexError: list index out of range
```

Vous voyez qu'à la position `0` se trouve "Kelly", à la position `1` se trouve "Nelly", à la position `2` se trouve "Jimmy" et à la position `3 se trouve "Lenny".

Quand on arrive à la position `4`, qui a été spécifiée avec `range(5)` qui indique les positions de `0 à 4`, il n'y a rien à imprimer et donc l'interpréteur jette une erreur.

Une façon de résoudre ce problème est de diminuer le nombre entier dans `range() `:

```py
names = ["Kelly", "Nelly", "Jimmy", "Lenny"]

for name in range(4):
    print(name)
    print(names[name])
    
#output

#0
#Kelly
#1
#Nelly
#2
#Jimmy
#3
#Lenny
```

Une autre façon de résoudre ce problème lorsqu'on utilise une boucle for est de passer la longueur de la liste comme argument à la fonction `range()`. Pour ce faire, vous utilisez la fonction Python intégrée `len()`, comme indiqué dans une section précédente :


```py
names = ["Kelly", "Nelly", "Jimmy", "Lenny"]

for name in range(len(names)):
    print(names[name])

#output

#Kelly
#Nelly
#Jimmy
#Lenny
```

Lorsque vous passez `len()` comme argument à `range()`, assurez-vous de ne pas faire l'erreur suivante :


```py
names = ["Kelly", "Nelly", "Jimmy", "Lenny"]

for name in range(len(names) + 1):
    print(names[name])
```

Après avoir exécuté le code, vous obtiendrez à nouveau un `IndexError : list index out of range error`:

```
#Kelly
#Nelly
#Jimmy
#Lenny
#Traceback (most recent call last):
#  File "/Users/dionysialemonaki/python_articles/demo.py", line 4, in <module>
#    print(names[name])
#IndexError: list index out of range
```


## Conclusion

Nous espérons que cet article vous a donné un aperçu de la raison pour laquelle l'erreur IndexError : list index out of range se produit et des moyens de l'éviter.

Si vous voulez en savoir plus sur Python, consultez la [certification Python de freeCodeCamp](https://www.freecodecamp.org/learn/scientific-computing-with-python/). Vous commencerez à apprendre d'une manière interactive et conviviale pour les débutants. Vous construirez également cinq projets à la fin pour mettre en pratique et aider à renforcer ce que vous avez appris.

Merci de votre lecture et bon codage !



