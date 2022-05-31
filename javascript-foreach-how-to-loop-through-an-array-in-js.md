https://www.freecodecamp.org/news/javascript-foreach-how-to-loop-through-an-array-in-js/

# JavaScript forEach - Comment parcourir en boucle un tableau en JS

La méthode JavaScript forEach est l'une des nombreuses façons de boucler des tableaux. Chaque méthode a des caractéristiques différentes, et c'est à vous, en fonction de ce que vous faites, de décider laquelle utiliser.

Dans cet article, nous allons examiner de plus près la méthode JavaScript forEach.

Considérons que nous avons le tableau suivant :

```js
const numbers = [1, 2, 3, 4, 5];
```
L'utilisation de la traditionnelle "boucle for" pour parcourir le tableau serait la suivante :

```js
for (i = 0; i < numbers.length; i++) {
  console.log(numbers[i]);
} 
```

## En quoi la méthode forEach( ) est-elle différente ?

La méthode forEach est également utilisée pour parcourir des tableaux en boucle, mais elle utilise une fonction différente de la classique "boucle for".

La méthode forEach transmet [une fonction de rappel](https://www.freecodecamp.org/news/javascript-callback-functions-what-are-callbacks-in-js-and-how-to-use-them/) pour chaque élément d'un tableau ainsi que les paramètres suivants :

- Valeur actuelle (obligatoire) - La valeur de l'élément actuel du tableau.
- Index (facultatif) - Le numéro d'index de l'élément courant.
- Array (facultatif) - L'objet tableau auquel appartient l'élément courant.

Laissez-moi vous expliquer ces paramètres étape par étape.

Tout d'abord, pour parcourir un tableau en boucle en utilisant la méthode forEach, vous avez besoin d'une fonction de rappel (ou fonction anonyme) :

```js
numbers.forEach(function() {
    // code
});
```

La fonction sera exécutée pour chaque élément du tableau. Elle doit prendre au moins un paramètre qui représente les éléments d'un tableau :

```js
numbers.forEach(function(number) {
    console.log(number);
});
```
C'est tout ce que nous avons besoin de faire pour boucler le tableau :


Vous pouvez également utiliser la représentation de la fonction flèche ES6 pour simplifier le code :

```js
numbers.forEach(number => console.log(number));
```

## Paramètres facultatifs
#### Index
Très bien, continuons avec les paramètres optionnels. Le premier est le paramètre "index", qui représente le numéro d'index de chaque élément.

En fait, nous pouvons voir le numéro d'index d'un élément si nous l'incluons comme second paramètre :

```js
numbers.forEach((number, index) => {
    console.log('Index: ' + index + ' Value: ' + number);
});
```

#### Tableau

Le paramètre array est le tableau lui-même. Il est également facultatif et peut être utilisé si nécessaire dans diverses opérations. Sinon, si on l'appelle, il sera simplement imprimé autant de fois que le nombre d'éléments du tableau :

```js
numbers.forEach((number, index, array) => {
    console.log(array);
});
```

Vous pouvez voir un exemple d'utilisation de la méthode forEach( ) dans cette vidéo :

## Support des navigateurs
La méthode Array.forEach est prise en charge par tous les navigateurs sauf IE version 8 ou antérieure :

Si vous voulez en savoir plus sur le développement Web, n'hésitez pas à visiter ma [chaîne Youtube](https://www.youtube.com/channel/UC1EgYPCvKCXFn8HlpoJwY3Q?view_as=subscriber).

Merci de votre lecture !




