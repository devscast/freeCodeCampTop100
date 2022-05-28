https://www.freecodecamp.org/news/use-svg-images-in-css-html/

# Comment utiliser les images SVG en CSS et HTML - Un tutoriel pour les débutants

###  SVG est l'abréviation de Scalable Vector Graphics. Il s'agit d'un type unique de format d'image pour les graphiques vectoriels écrits en langage de balisage extensible (XML).

Dans ce tutoriel, je vais vous expliquer pourquoi vous souhaitez utiliser des images SVG et comment vous pouvez les utiliser en CSS et en HTML.


## Pourquoi utiliser des images SVG ?

Il existe un certain nombre de raisons d'utiliser des images SVG, dont voici quelques-unes :

- Les images SVG ne perdent pas leur qualité lorsqu'elles sont zoomées ou redimensionnées.
- Elles peuvent être créées et modifiées avec un IDE ou un éditeur de texte.
- Elles sont accessibles et animables.
- Elles ont une petite taille de fichier et sont hautement évolutives.
- Et ils peuvent être recherchés, indexés, scriptés et compressés.
Voyons maintenant comment vous pouvez réellement travailler avec des images SVG.

## Comment télécharger l'image SVG utilisée dans ce tutoriel

Si vous voulez travailler avec l'image SVG que j'ai utilisée dans ce tutoriel, suivez les étapes (et le diagramme) ci-dessous pour la télécharger.

- Allez sur [unDraw](https://undraw.co/).
- Changez la couleur de fond en jaune.
- Dans le champ de recherche, recherchez le mot **happy**.
- Cliquez sur l'image nommée **Happy news**.
- Dans la fenêtre pop-up, cliquez sur le bouton **Download SVG** vers vos projets.

Si vous avez suivi les étapes ci-dessus correctement, l'image SVG devrait être sur votre ordinateur maintenant.

Maintenant, ouvrez l'image SVG dans votre IDE ou éditeur de texte préféré. Renommez-la en **happy.svg** ou tout autre nom que vous préférez.

## How to use SVG images in CSS and HTML

There are several different ways to use SVG images in CSS and HTML. We will explore six different methods in this tutorial.

1. How to use an SVG as an `<img>`
This method is the simplest way to add SVG images to a webpage. To use this method, add the `<img>` element to your HTML document and reference it in the `src` attribute, like this:

```html
<img src = "happy.svg" alt="My Happy SVG"/>
```

En supposant que vous avez téléchargé l'image SVG depuis unDraw et que vous l'avez renommée en **happy.svg**, vous pouvez aller de l'avant et ajouter l'extrait de code ci-dessus dans votre document HTML.

Si vous avez tout fait correctement, votre page Web devrait ressembler exactement à la démo ci-dessous. 👀

Lorsque vous ajoutez une image SVG à l'aide de la balise `<img>` sans en spécifier la taille, elle prend la taille du fichier SVG original.

Par exemple, dans la démo ci-dessus, je n'ai pas modifié la taille de l'image SVG, elle a donc repris sa taille d'origine (qui était une largeur de `915,11162px` et une hauteur de `600,53015px` ).

Note : pour modifier la taille originale, vous devez spécifier la `largeur` et la 'hauteur' avec CSS comme vous pouvez le voir dans la démo ci-dessous. Vous pouvez également mettre à jour la `largeur` et la `hauteur` d'origine directement.

Même si nous pouvons modifier la taille des images SVG ajoutées via la balise `<img>`, il existe encore quelques restrictions si vous souhaitez apporter des changements de style importants à l'image SVG.

2. How to use SVG as a CSS background-image
This is similar to adding SVG to an HTML document using the `<img>` tag. But this time we do it with CSS instead of HTML as you can see in the code snippet below.


```css
body {
  background-image: url(happy.svg);
}
```
Lorsque vous utilisez un SVG comme image d'arrière-plan CSS, les limites sont similaires à celles de l'utilisation de `<img>`. Pourtant, il permet un peu plus de personnalisation.

Consultez la démo ci-dessous et n'hésitez pas à y apporter des modifications à l'aide de CSS.

3. Comment utiliser les images SVG en ligne
Les images SVG peuvent être écrites directement dans le document HTML à l'aide de la balise`<svg></svg>`.

Pour ce faire, ouvrez l'image SVG dans VS code ou votre IDE préféré, copiez le code et collez-le dans l'élément `<body>` de votre document HTML.

```html
<body>
 // Paste the SVG code here.
</body>
```
Si vous avez tout fait correctement, votre page Web devrait ressembler exactement à la démonstration ci-dessous.

Lorsque vous utilisez SVG en ligne dans le document HTML, cela réduit le temps de chargement car il sert de requête HTTP. L'utilisation de cette méthode vous permet d'effectuer plus de personnalisation plutôt que d'utiliser les méthodes `<img>` ou `background-image`.

4. Comment utiliser un SVG comme <object>

Vous pouvez également utiliser un élément HTML <object> pour ajouter des images SVG à une page Web en utilisant la syntaxe de code ci-dessous :

```
<object data="happy.svg" width="300" height="300"> </object>
```

Vous utilisez l'attribut `data` pour spécifier l'URL de la ressource que vous utiliserez par l'objet, qui est l'image SVG dans notre cas.

Vous utilisez la `width` et `height` pour spécifier la taille de l'image SVG.

Encore une fois, vous trouverez ci-dessous une démo à explorer. 😃

L'utilisation de <object> est prise en charge dans tous les navigateurs prenant en charge SVG.

5. Comment utiliser SVG comme <iframe>

Même si cela n'est pas conseillé, vous pouvez également ajouter une image SVG à l'aide d'un <iframe> comme indiqué dans la démo ci-dessous.

Gardez simplement à l'esprit, cependant, que les <iframe> peuvent être difficiles à maintenir et seront mauvais pour l'optimisation pour les moteurs de recherche (SEO) de votre site.

L'utilisation de <iframe> va également à l'encontre de l'objectif de Scalable dans le nom *Scalable Vector Graphics* car les images SVG ajoutées avec ce format ne sont pas évolutives.

6. Comment utiliser SVG comme <embed>

L'élément HTML <embed> est une autre façon d'utiliser une image SVG en HTML et CSS en utilisant cette syntaxe : `<embed src="happy.svg" />`.

Gardez à l'esprit, cependant, que cette méthode a également des limites. Selon MDN, la plupart des navigateurs modernes ont déprécié et supprimé la prise en charge des plug-ins de navigateur. Cela signifie que s'appuyer sur <embed> n'est généralement pas judicieux si vous souhaitez que votre site soit utilisable sur le navigateur de l'utilisateur moyen.

Vous trouverez ci-dessous une démonstration de l'utilisation de l'élément HTML <embed> pour ajouter une image SVG.

Conclusion

J'espère que vous avez pu en apprendre davantage sur les différentes manières d'utiliser les images SVG en CSS et HTML. Cela vous guidera, espérons-le, vers la bonne méthode lors de l'ajout d'images SVG à un site Web.