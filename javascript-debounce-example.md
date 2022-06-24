https://www.freecodecamp.org/news/javascript-debounce-example/
# Debounce - Comment retarder une fonction en JavaScript (exemple JS ES6)

![](https://www.freecodecamp.org/news/content/images/size/w2000/2021/01/teaser.jpg)

En JavaScript, une fonction de débordement permet de s'assurer que votre code n'est déclenché qu'une seule fois par entrée utilisateur. Les suggestions des boîtes de recherche, l'enregistrement automatique des champs de texte et l'élimination des doubles clics sur les boutons sont autant de cas d'utilisation de la fonction debounce.

Dans ce tutoriel, nous allons apprendre à créer une fonction de débordement en JavaScript.

## Qu'est-ce que le rebond ?

Le terme "rebond" vient de l'électronique. Lorsque vous appuyez sur un bouton, disons sur la télécommande de votre téléviseur, le signal se déplace vers la micropuce de la télécommande si rapidement qu'avant que vous ne parveniez à relâcher le bouton, il rebondit et la micropuce enregistre votre "clic" plusieurs fois.

![](https://www.freecodecamp.org/news/content/images/2021/01/debounce-button.png)

Pour atténuer ce problème, une fois qu'un signal provenant du bouton est reçu, la micropuce arrête de traiter les signaux provenant du bouton pendant quelques microsecondes, le temps qu'il vous soit physiquement impossible d'appuyer à nouveau sur le bouton.

## Debounce en JavaScript

En JavaScript, le cas d'utilisation est similaire. Nous voulons déclencher une fonction, mais seulement une fois par cas d'utilisation.

Disons que nous voulons afficher des suggestions pour une requête de recherche, mais seulement après que le visiteur ait fini de la taper.

Ou bien nous voulons enregistrer les modifications apportées à un formulaire, mais uniquement lorsque l'utilisateur n'est pas en train de travailler activement sur ces modifications, car chaque "enregistrement" nous coûte un voyage dans la base de données.

Et mon préféré : certaines personnes se sont vraiment habituées à Windows 95 et font maintenant un double clic sur tout 😁.

Voici une mise en œuvre simple de la fonction de débordement ([CodePen ici](https://codepen.io/ondrabus/pen/WNGaVZN)):

```js
function debounce(func, timeout = 300){
  let timer;
  return (...args) => {
    clearTimeout(timer);
    timer = setTimeout(() => { func.apply(this, args); }, timeout);
  };
}
function saveInput(){
  console.log('Saving data');
}
const processChange = debounce(() => saveInput());
```

Il peut être utilisé sur une entrée :

```html
<input type="text" onkeyup="processChange()" />
```

Ou un bouton :

```html
<button onclick="processChange()">Clique moi</button>
```

Ou un événement sur Window :

```js
window.addEventListener("scroll", processChange);
```

Et sur d'autres éléments comme une simple fonction JS.

Alors, que se passe-t-il ici ? `debounce` est une fonction spéciale qui gère deux tâches :

- Attribution d'une portée pour la variable *timer*
- Planifier le déclenchement de votre fonction à un moment précis

Expliquons comment cela fonctionne dans le premier cas d'utilisation avec la saisie de texte.

Lorsqu'un visiteur écrit la première lettre et relâche la touche, le `debounce` réinitialise d'abord le timer avec `clearTimeout(timer)`. À ce stade, l'étape n'est pas nécessaire car il n'y a encore rien de programmé. Ensuite, il programme la fonction fournie - `saveInput()` - pour qu'elle soit invoquée dans 300 ms.

Mais disons que le visiteur continue à écrire, donc chaque relâchement de touche déclenche à nouveau le `debounce`. Chaque invocation doit réinitialiser la minuterie, ou, en d'autres termes, annuler les plans précédents avec `saveInput(`), et les reprogrammer pour un nouveau moment - 300 ms dans le futur. Cela continue aussi longtemps que le visiteur continue à frapper les touches sous 300 ms.

Le dernier planning ne sera pas effacé et la fonction `saveInput()` sera finalement appelée.

## Dans l'autre sens : comment ignorer les événements ultérieurs

C'est bien pour déclencher l'enregistrement automatique ou afficher des suggestions. Mais qu'en est-il du cas d'utilisation avec plusieurs clics sur un même bouton ? Nous ne voulons pas attendre le dernier clic, mais plutôt enregistrer le premier et ignorer les autres.

([CodePen ici](https://codepen.io/ondrabus/pen/bGwmXjN)).

```js
function debounce_leading(func, timeout = 300){
  let timer;
  return (...args) => {
    if (!timer) {
      func.apply(this, args);
    }
    clearTimeout(timer);
    timer = setTimeout(() => {
      timer = undefined;
    }, timeout);
  };
}
```

Ici, nous déclenchons la fonction `saveInput()` lors du premier appel de `debounce_leading` provoqué par le premier clic sur le bouton. Nous programmons la destruction du timer pour 300 ms. Chaque clic de bouton suivant dans ce laps de temps aura déjà le timer défini et ne fera que repousser la destruction de 300 ms dans le futur.

## Implémentations de la fonction debounce dans les librairies

Dans cet article, je vous ai montré comment implémenter une fonction de rebond en JavaScript et l'utiliser pour, eh bien, rebondir sur des événements déclenchés par des éléments de site Web.

Cependant, vous n'avez pas besoin d'utiliser votre propre implémentation de debounce dans vos projets si vous ne le souhaitez pas. Des bibliothèques JS largement utilisées contiennent déjà son implémentation. En voici quelques exemples :

|_**Librarie**_| _**Exemple**_ |
|--|--|
| [jQuery (via library)](http://benalman.com/projects/jquery-throttle-debounce-plugin/)|`$.debounce(300, saveInput);`|
|[Lodash](https://lodash.com/docs/4.17.15#debounce)|`_.debounce(saveInput, 300);`|
|[Underscore](https://underscorejs.org/#debounce)|`_.debounce(saveInput, 300);`|
