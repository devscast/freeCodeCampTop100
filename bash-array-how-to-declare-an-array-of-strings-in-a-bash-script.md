# Bash Array - Comment déclarer un tableau de chaînes de caractères dans un script Bash ?

![Image cover](https://www.freecodecamp.org/news/content/images/size/w2000/2021/09/pexels-belle-co-1000445.jpg)

Les scripts Bash constituent un moyen pratique d'automatiser les tâches en ligne de commande.

Avec Bash, vous pouvez faire la plupart des choses que vous feriez dans d'autres langages de script ou de programmation. Vous pouvez créer et utiliser des variables, exécuter des boucles, utiliser une logique conditionnelle et stocker des données dans des tableaux.

Bien que la fonctionnalité puisse être très familière, la syntaxe de Bash peut être délicate. Dans cet article, vous apprendrez à déclarer des tableaux, puis à les utiliser dans votre code.

## Comment déclarer un tableau en Bash ?

Déclarer un tableau en Bash est facile, mais faites attention à la syntaxe. Si vous avez l'habitude de programmer dans d'autres langages, le code peut vous sembler familier, mais il existe des différences subtiles qui sont faciles à manquer.

Pour déclarer votre tableau, suivez les étapes suivantes :

1. Donnez un nom à votre tableau
2. Faites suivre ce nom de variable d'un signe égal. Le signe égal ne doit pas être entouré d'espaces.
3. Placez le tableau entre parenthèses (et non entre crochets comme en JavaScript).
4. Tapez vos chaînes de caractères en utilisant des guillemets, mais sans virgule entre elles.

Votre déclaration de tableau ressemblera à quelque chose comme ceci :

```sh
myArray=("cat" "dog" "mouse" "frog)
```

C'est tout ! C'est aussi simple que cela.

## Comment accéder à un tableau en Bash

Il y a plusieurs façons de boucler dans votre tableau. Vous pouvez soit boucler sur les éléments eux-mêmes, soit boucler sur les indices.

### Comment boucler sur les éléments d'un tableau

Pour boucler sur les éléments d'un tableau, votre code devra ressembler à quelque chose comme ceci :

```sh
for str in ${myArray[@]}; do
  echo $str
done
```

Pour décomposer cela : c'est un peu comme utiliser `forEach` en JavaScript. Pour chaque chaîne (str) du tableau (myArray), imprimez cette chaîne.

La sortie de cette boucle ressemble à ceci :

```
cat
dog
mouse
frog
```

**Remarque** : le symbole `@` entre les crochets indique que vous parcourez en boucle tous les éléments du tableau. Si vous l'omettez et écrivez simplement `for str in ${myArray}`, seule la première chaîne du tableau sera imprimée.

### Comment boucler sur les indices d'un tableau
Une autre solution consiste à parcourir les indices du tableau en boucle. Cela ressemble à une boucle `for` en JavaScript, et est utile lorsque vous souhaitez accéder à l'indice de chaque élément.

Pour utiliser cette méthode, votre code devra ressembler à ce qui suit :

```sh
for i in ${!myArray[@]}; do
  echo "element $i is ${myArray[$i]}"
done
```
La sortie ressemblera à ceci :

```
element 0 is cat
element 1 is dog
element 2 is mouse
element 3 is frog
```


**Remarque** : le point d'exclamation au début de la variable `myArray` indique que vous accédez aux indices du tableau et non aux éléments eux-mêmes. Cela peut être déroutant si vous êtes habitué à ce que le point d'exclamation indique la négation, alors faites bien attention à cela.

**Autre remarque** : Bash ne requiert généralement pas d'accolades pour les variables, mais il le fait pour les tableaux. Vous remarquerez donc que lorsque vous faites référence à un tableau, vous le faites avec la syntaxe `${myArray}`, mais que lorsque vous faites référence à une chaîne ou à un nombre, vous utilisez simplement le signe dollar : `$i`.

## Conclusion
Les scripts Bash sont utiles pour créer un comportement automatisé en ligne de commande, et les tableaux sont un outil formidable que vous pouvez utiliser pour stocker plusieurs éléments de données.

Les déclarer et les utiliser n'est pas difficile, mais c'est différent des autres langages, alors faites bien attention pour éviter de faire des erreurs.
