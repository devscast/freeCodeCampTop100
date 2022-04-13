https://www.freecodecamp.org/news/check-if-javascript-array-is-empty-or-not-with-length/

# Comment vérifier si un tableau JavaScript est vide ou non avec .length ?

Lorsque vous programmez en JavaScript, vous pouvez avoir besoin de savoir comment vérifier si un tableau est vide ou non.

Pour vérifier si un tableau est vide ou non, vous pouvez utiliser la propriété .length.

La propriété length définit ou renvoie le nombre d'éléments d'un tableau. En connaissant le nombre d'éléments d'un tableau, vous pouvez savoir s'il est vide ou non. Un tableau vide contient `0` élément.

Prenons quelques exemples.

## .length Exemple de syntaxe


```javascript
Const myArray = [‘Horses’, ‘Dogs’, ‘Cats’];
```

Ici, nous créons une variable pointant vers un tableau.

En utilisant la propriété length, nous pouvons vérifier la longueur du tableau :

```javascript
myArray.length
```

Cela renverra 3, car il y a 3 éléments dans le tableau.

Pour vérifier si le tableau est vide ou non avec .length, nous pouvons le faire de trois manières différentes.

## .length exemple un

Tout d'abord, créons un nouveau tableau sans éléments.


```javascript
const arr = []
```

Maintenant nous pouvons vérifier si le tableau est vide en utilisant `.length`.

```javascript
arr.length
```

Cela retournera 0, car il y a 0 éléments dans le tableau.

## .length exemple deux

Nous pouvons également vérifier explicitement si le tableau est vide ou non.

`if (arr.length === 0) { console.log("Le tableau est vide !") }`

Si notre tableau est vide, le message ci-dessus sera enregistré. Si le tableau contient des éléments, le code contenu dans le bloc `if` ne sera pas exécuté.

Voici la troisième façon de vérifier si un tableau est vide ou non en utilisant .length.

## .length exemple trois

En combinant l'utilisation de la propriété length et l'opérateur logique "not" en JavaScript, le symbole " !", nous pouvons vérifier si un tableau est vide ou non.

L'opérateur `!` annule une expression. Autrement dit, nous pouvons l'utiliser pour renvoyer `True` si un tableau est vide.

Pour cet exemple, ouvrons notre console JavaScript. Pour ouvrir votre console dans Chrome, vous pouvez cliquer sur Inpsect -> Console.

Tout d'abord, créez un tableau ne contenant aucun élément.

Ensuite, utilisons l'opérateur logique "not", ainsi que notre propriété .length, pour tester si le tableau est vide ou non.

Si nous n'avions pas utilisé l'opérateur "not", `arr.length` aurait retourné `0`. Avec l'opérateur ajouté, il retournera `True` si son opérande est `False`. Parce que arr.length est `0`, ou faux, il renvoie `True`.

Utilisons ceci avec une instruction `if`, et affichons un message si notre tableau est vide.

Lorsque l'on vérifie si un tableau est vide ou non, il est souvent préférable de vérifier également si le tableau est bien un tableau.

Pourquoi ?  

Parce qu'il peut arriver que vous vous attendiez à vérifier la longueur d'un tableau, mais qu'on vous donne un autre type de données, par exemple une chaîne de caractères :


Comme la `length property` peut être utilisée sur d'autres types de données, il est bon de vérifier également que votre tableau est bien un tableau comme vous l'attendiez.

Je vous suggère d'utiliser également la méthode `Array.isArray()` pour confirmer que votre tableau est un tableau. Cette méthode détermine si ce qui a été transmis est un tableau ou non. Si ce qui a été transmis est un tableau, cette méthode renvoie `true`.

Ajoutons cette méthode à notre exemple.

## Utilisation de la méthode Array.isArray()

## Conclusion

Dans cet article, nous avons appris que vous pouvez utiliser la propriété `length` en JavaScript de différentes manières pour vérifier si un tableau est vide ou non. La propriété `length` renvoie le nombre d'éléments d'un tableau.

Nous avons également appris qu'il est préférable d'utiliser également la méthode `Array.isArray` lorsque vous utilisez la propriété `.length`, afin de vérifier si la valeur transmise est un tableau comme vous l'attendez.
