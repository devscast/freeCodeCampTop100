https://www.freecodecamp.org/news/how-to-use-html-to-open-link-in-new-tab/

# Comment utiliser le HTML pour ouvrir un lien dans un nouvel onglet ?

Les onglets sont géniaux, n'est-ce pas ? Ils permettent au "multitâcheur" qui sommeille en chacun de nous de jongler avec plusieurs tâches en ligne en même temps.

Les onglets sont désormais si courants que, lorsque vous cliquez sur un lien, il est probable qu'il s'ouvre dans un nouvel onglet.

Si vous vous êtes déjà demandé comment faire cela avec vos propres liens, vous êtes au bon endroit.


## L'élément Ancre
Pour créer un lien sur une page Web, vous devez entourer un élément (texte, image, etc.) d'un élément ancre (`<a>`) et définir son attribut href sur l'URL vers laquelle vous souhaitez créer le lien.

```html
<p>Check out <a href="https://www.freecodecamp.org/">freeCodeCamp</a>.</p>
```

Check out [freeCodeCamp](https://www.freecodecamp.org/).

Si vous cliquez sur le lien ci-dessus, le navigateur ouvrira le lien dans la fenêtre ou l'onglet actuel. C'est le comportement par défaut de tous les navigateurs.

Pour ouvrir un lien dans un nouvel onglet, nous devons examiner certains des autres attributs de l'élément ancre.


## L'attribut Target
Cet attribut indique au navigateur comment ouvrir le lien.

Pour ouvrir un lien dans un nouvel onglet, il suffit de définir l'attribut `target` sur `_blank` :

```html
<p>Check out <a href="https://www.freecodecamp.org/" target="_blank">freeCodeCamp</a>.</p>
```

Désormais, lorsque quelqu'un clique sur le lien, celui-ci s'ouvre dans un nouvel onglet, ou éventuellement dans une nouvelle fenêtre selon les paramètres du navigateur de la personne.


## Problèmes de sécurité liés à l'utilisation de `target="_blank"`.

Je recommande vivement de toujours ajouter `rel="noreferrer noopener"` à l'élément ancre chaque fois que vous utilisez 
l'attribut `target` :

```html
<p>Check out <a href="https://www.freecodecamp.org/" target="_blank" rel="noopener noreferrer">freeCodeCamp</a>.</p>
```

Ceci aboutit à un résultat suivant :

Check out <a href="https://www.freecodecamp.org/" target="_blank" rel="noopener noreferrer">freeCodeCamp</a>.

L'attribut rel définit la relation entre votre page et l'URL liée. Le définir sur `noopener noreferrer` permet d'éviter un type de phishing connu sous le nom de [tabnabbing](https://en.wikipedia.org/wiki/Tabnabbing).


## Qu'est-ce que le tabnabbing ?
Le tabnabbing, parfois appelé reverse tabnabbing, est un exploit qui utilise le comportement par défaut du navigateur avec `target="_blank"` pour obtenir un accès partiel à votre page via l'API `window.object`.

Avec le tabnabbing, une page vers laquelle vous avez créé un lien peut faire en sorte que votre page soit redirigée vers une fausse page de connexion. La plupart des utilisateurs ne s'en apercevraient pas, car ils se concentreraient sur l'onglet qui vient de s'ouvrir, et non sur l'onglet d'origine contenant votre page.

Ensuite, lorsqu'une personne revient à l'onglet contenant votre page, elle voit la fausse page de connexion et peut entrer ses données de connexion.

Si vous souhaitez en savoir plus sur le fonctionnement du tabnabbing et sur les possibilités offertes par l'exploit, consultez [l'article d'Alex Yumashev](https://www.jitbit.com/alexblog/256-targetblank---the-most-underestimated-vulnerability-ever/) et celui de [l'OWASP](https://owasp.org/www-community/attacks/Reverse_Tabnabbing).

Si vous souhaitez voir un exemple de fonctionnement sûr, consultez cette [page](https://mathiasbynens.github.io/rel-noopener/) et son [repo GitHub](https://github.com/mathiasbynens/rel-noopener) pour plus d'informations sur l'exploit et l'attribut `rel`.


# En résumé

Il est facile d'utiliser le HTML pour ouvrir un lien dans un nouvel onglet. Il suffit d'avoir un élément ancre (`<a>`) avec trois attributs importants :

- L'attribut `href` défini sur l'URL de la page vers laquelle vous souhaitez créer un lien.

- L'attribut `target` défini sur `_blank`, qui indique au navigateur d'ouvrir le lien dans un nouvel onglet ou une nouvelle fenêtre, selon les paramètres du navigateur.

- L'attribut `rel` est défini sur `noreferrer noopener` afin d'éviter d'éventuelles attaques malveillantes de la part des pages vers lesquelles vous établissez un lien.


Encore une fois, voici un exemple fonctionnel complet :

```html
<p>Check out <a href="https://www.freecodecamp.org/" target="_blank" rel="noopener noreferrer">freeCodeCamp</a>.</p>
```

Ce qui donne la sortie suivante dans le navigateur :

Check out <a href="https://www.freecodecamp.org/" target="_blank" rel="noopener noreferrer">freeCodeCamp</a>.</p>.

Merci encore pour votre lecture. Bon codage.
