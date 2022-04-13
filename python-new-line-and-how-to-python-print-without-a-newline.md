https://www.freecodecamp.org/news/python-new-line-and-how-to-python-print-without-a-newline/

# Python New Line et comment imprimer en Python sans Newline

Bienvenue ! Le caractère de nouvelle ligne en Python est utilisé pour marquer la fin d'une ligne et le début d'une nouvelle ligne. Il est essentiel de savoir comment l'utiliser si vous voulez imprimer des données dans la console et travailler avec des fichiers.

Dans cet article, vous apprendrez :

. Comment identifier le caractère de nouvelle ligne en Python.
. Comment le caractère de nouvelle ligne peut être utilisé dans les chaînes de caractères et les instructions d'impression.
. Comment écrire des instructions d'impression qui n'ajoutent pas de caractère de nouvelle ligne à la fin de la chaîne.

C'est parti ! ✨

## 🔹 Le nouveau caractère de ligne

Le caractère de nouvelle ligne en Python est :

```
\n
```

Il est composé de deux caractères :

. Une barre oblique inversée.
. La lettre n.

Si vous voyez ce caractère dans une chaîne de caractères, cela signifie que la ligne actuelle se termine à cet endroit et qu'une nouvelle ligne commence juste après :


Vous pouvez également utiliser ce caractère dans  *f-strings*:

```python
>>> print(f"Hello\nWorld!")
```


## 🔸 Le caractère de nouvelle ligne dans les instructions d'impression

Par défaut, les instructions print ajoutent un caractère de nouvelle ligne " en coulisse " à la fin de la chaîne.

Comme ceci :

Cela se produit parce que, selon la [documentation Python](https://docs.python.org/3/library/functions.html#print) :

La valeur par défaut du paramètre `end` de la fonction `print` intégrée est `\n`, donc un caractère de nouvelle ligne est ajouté à la chaîne.

💡 *Conseil* : Append signifie "ajouter à la fin".

Voici la définition de la fonction :

Remarquez que la valeur de `end` est `\n`, et qu'il sera ajouté à la fin de la chaîne.

Si vous n'utilisez qu'une seule instruction print, vous ne le remarquerez pas car une seule ligne sera imprimée :

Mais si vous utilisez plusieurs instructions d'impression l'une après l'autre dans un script Python :

La sortie sera imprimée sur des lignes séparées car `\n` a été ajouté "en coulisses" à la fin de chaque ligne :

## 🔹 Comment imprimer sans nouvelle ligne ?

Nous pouvons modifier ce comportement par défaut en personnalisant la valeur du paramètre `end` de la fonction `print`.

Si nous utilisons la valeur par défaut dans cet exemple :

Nous voyons la sortie imprimée en deux lignes :

Mais si nous personnalisons la valeur de `end` et la définissons comme `" "`.

Un espace sera ajouté à la fin de la chaîne au lieu du caractère de nouvelle ligne `\n`, de sorte que la sortie des deux instructions d'impression sera affichée sur la même ligne :

Vous pouvez l'utiliser pour imprimer une séquence de valeurs sur une seule ligne, comme dans cet exemple :

```

```
Le résultat est :


```
```

💡 *Conseil* : Nous ajoutons une instruction conditionnelle pour nous assurer que la virgule ne sera pas ajoutée au dernier numéro de la séquence.

De même, nous pouvons l'utiliser pour imprimer les valeurs d'un itérable sur la même ligne :

```
```

Le résultat est :


```
```

🔸 Le nouveau caractère de ligne dans les fichiers
Le caractère de nouvelle ligne `\n` se trouve également dans les fichiers, mais il est "caché". Lorsque vous voyez une nouvelle ligne dans un fichier texte, un caractère de nouvelle ligne `\n` a été inséré.

Vous pouvez le vérifier en lisant le fichier avec `<file>.readlines()`, comme ceci :


```python
with open("names.txt", "r") as f:
    print(f.readlines())
```
Le résultat est :

```
```

Comme vous pouvez le constater, les trois premières lignes du fichier texte se terminent par une nouvelle ligne `\n` caractère qui travaille "en coulisses".

💡 *Astuce* : Remarquez que seule la dernière ligne du fichier ne se termine pas par un caractère de nouvelle ligne.


## 🔹 En résumé

. Le caractère de nouvelle ligne en Python est le `\n`. Il est utilisé pour indiquer la fin d'une ligne de texte.
. Vous pouvez imprimer des chaînes de caractères sans ajouter une nouvelle ligne avec `end = <caractère>`, lequel `<caractère>` est le caractère qui sera utilisé pour séparer les lignes.
J'espère vraiment que vous avez aimé mon article et qu'il vous a été utile. Vous pouvez maintenant travailler avec le caractère de nouvelle ligne en Python.

