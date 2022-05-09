https://www.freecodecamp.org/news/python-empty-list-tutorial-how-to-create-an-empty-list-in-python/

# Tutoriel Python sur les listes vides - Comment créer une liste vide en Python

Si vous souhaitez apprendre à créer efficacement une liste vide en Python, cet article est fait pour vous.

Vous allez apprendre :

- Comment créer une liste vide en utilisant les crochets [].
- Comment créer une liste vide en utilisant list().
- Leurs cas d'utilisation.
- Leur efficacité (l'une est plus rapide que l'autre !). Nous utiliserons le module timeit pour les comparer.
C'est parti ! ✨

## 🔹 Utilisation des crochets
Vous pouvez créer une liste vide avec une paire vide de crochets, comme ceci :  

💡 Conseil : Nous affectons la liste vide à une variable pour l'utiliser plus tard dans notre programme.

Par exemple :

```
num = []
```

La liste vide aura une longueur de `0`, comme vous pouvez le voir ici :

```py
>>> num = []
>>> len(num)
0
```

Les listes vides sont des valeurs fausses, ce qui signifie qu'elles ont la valeur False dans un contexte `False` :

```python
>>> num = []
>>> bool(num)
False
```

## Ajouter des éléments à une liste vide

Vous pouvez ajouter des éléments à une liste vide à l'aide des méthodes `append()` et `insert()` :

- `append()` ajoute l'élément à la fin de la liste.
- `insert()` ajoute l'élément à l'index particulier de la liste que vous avez choisi.
Puisque les listes peuvent être des valeurs véridiques ou fausses selon qu'elles sont vides ou non lorsqu'elles sont évaluées, vous pouvez les utiliser dans des conditionnelles comme celle-ci :

```python 
if num:
	print("This list is not empty")
else:
	print("This list is empty")
```

La sortie de ce code est :

```
This list is empty
```

Parce que la liste était vide, il évalue donc à False.

En général :

* Si la liste n'est pas vide, elle est évaluée à `True`, donc la clause if est exécutée.
* Si la liste est vide, elle vaut `False`, et la clause else est exécutée.

### Exemple :

Dans l'exemple ci-dessous, nous créons une liste vide et l'affectons à la variable `num`. Puis, à l'aide d'une boucle for, nous ajoutons une séquence d'éléments (entiers) à la liste qui était initialement vide :

```python 
>>> num = []
>>> for i in range(3, 15, 2):
	num.append(i)
```

Nous vérifions la valeur de la variable pour voir si les éléments ont été ajoutés avec succès et confirmons que la liste n'est plus vide :  

```py
>>> num
[3, 5, 7, 9, 11, 13]
```

💡 Astuce : Nous utilisons couramment `append()` pour ajouter le premier élément à une liste vide, mais vous pouvez également ajouter cet élément en appelant la méthode `insert()` avec l'indice `0` :

```py
>>> num = []
>>> num.insert(0, 1.5) # add the float 1.5 at index 0
>>> num
[1.5]
```

## 🔸Utilisation du constructeur list()

Vous pouvez également créer une liste vide à l'aide du constructeur de type `list()`, qui crée un nouvel objet liste.

Selon la [documentation Python](https://docs.python.org/3/library/stdtypes.html#list) :

> Si aucun argument n'est donné, le constructeur crée une nouvelle liste vide, `[]`.

*💡 Conseil : Cela crée un nouvel objet liste en mémoire et comme nous n'avons passé aucun argument à list(), une liste vide sera créée.

Par exemple :

```
num = list()
```

Cette liste vide aura une longueur de 0, comme vous pouvez le voir ici : 

```py
>>> num = list()
>>> len(num)
0
```

Et il s'agit d'une valeur fictive lorsqu'elle est vide (elle vaut False dans un contexte booléen) : 

```py
>>> num = list()
>>> bool(num)
False
```

### Exemple :

Il s'agit d'une liste entièrement fonctionnelle, nous pouvons donc y ajouter des éléments :

```py
>>> num = list()
>>> for i in range(3, 15, 2):
	num.append(i)
```

Et le résultat sera une liste non vide, comme vous pouvez le voir ici :

```py
>>> num
[3, 5, 7, 9, 11, 13]
```

## 🔹 Cas d'utilisation

Nous utilisons généralement `list()` pour créer des listes à partir d'itérables existants tels que des chaînes de caractères, des dictionnaires ou des tuples.
Vous verrez couramment des crochets `[]` être utilisés pour créer des listes vides en Python, car cette syntaxe est plus concise et plus rapide.

## 🔸 Efficacité

Attendez ! Je viens de vous dire que `[]` est plus rapide que `list()`...

### Mais de combien ?

Vérifions leurs efficacités temporelles à l'aide du module timeit.

Pour utiliser ce module dans votre programme Python, vous devez l'importer :


```py
>>> import timeit
```

Plus précisément, nous utiliserons la [fonction timeit](https://docs.python.org/3/library/timeit.html#timeit.timeit) de ce module, que vous pouvez appeler avec cette syntaxe :

* 💡 Conseil : Le code est répété plusieurs fois pour réduire les différences de temps qui peuvent provenir de facteurs externes tels que d'autres processus qui pourraient être en cours d'exécution à ce moment précis. Les résultats sont ainsi plus fiables à des fins de comparaison.

*🚦 A vos marques... prêts... prêts* ! Voici le code et le résultat :

Tout d'abord, nous importons le module.

```py
>>> import timeit
```

Ensuite, nous commençons à tester chaque syntaxe.

### Testing `[]`:

```py
>>> timeit.timeit('[]', number=10**4)
0.0008467000000109692
```

### Testing `list()`:

```py
>>> timeit.timeit('list()', number=10**4)
0.002867799999989984
```

💡 Conseil : Remarquez que le code que vous voulez chronométrer doit être entouré de guillemets simples `''` ou de guillemets doubles` ""`. Le temps renvoyé par la fonction `timeit` est exprimé en secondes.

Comparez ces résultats :

- `[]` : `0.0008467000000109692`
- `list()` : `0.002867799999989984`

Vous pouvez voir que `[]` est beaucoup plus rapide que `list()`. La différence est d'environ `0,002` seconde dans ce test :


```py
>>> 0.002867799999989984 - 0.0008467000000109692
0.0020210999999790147
```

Je suis sûr que vous devez vous poser la question en ce moment : Pourquoi `list()` est-elle moins efficace que `[]` si elles font exactement la même chose ?

Eh bien... `list()` est plus lent parce qu'il faut chercher le nom de la fonction, l'appeler, puis créer l'objet liste en mémoire. En revanche,`[]` est comme un "raccourci" qui ne nécessite pas autant d'étapes intermédiaires pour créer la liste en mémoire.

Cette différence de temps n'affectera pas beaucoup les performances de votre programme, mais il est bon de savoir laquelle est la plus efficace et comment elles fonctionnent en coulisses.


## 🔹 En résumé
Vous pouvez créer une liste vide en utilisant une paire vide de crochets `[]` ou le constructeur de type `list()`, une fonction intégrée qui crée une liste vide lorsqu'aucun argument n'est passé.

Les crochets `[]` sont couramment utilisés en Python pour créer des listes vides car ils sont plus rapides et plus concis.

*J'espère vraiment que mon article vous a plu et qu'il vous a été utile*. Vous pouvez maintenant créer des listes vides dans vos projets Python. Consultez mes cours en ligne. Suivez-moi sur Twitter. ⭐️

Si vous voulez plonger plus profondément dans les listes, vous aimerez peut-être lire :

- [Python List Append – How to Add an Element to an Array, Explained with Examples](https://www.freecodecamp.org/news/python-list-append-how-to-add-an-element-to-an-array-explained-with-examples/)
- [The Python Sort List Array Method – Ascending and Descending Explained with Examples](https://www.freecodecamp.org/news/the-python-sort-list-array-method-ascending-and-descending-explained-with-examples/)
- [Python List Append VS Python List Extend – The Difference Explained with Array Method Examples](https://www.freecodecamp.org/news/python-list-append-vs-python-list-extend/)