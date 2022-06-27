https://www.freecodecamp.org/news/how-to-center-an-image-in-css/

# Comment centrer une image verticalement et horizontalement avec CSS

![](https://cdn-media-2.freecodecamp.org/w1280/5f9c9a4c740569d1a4ca24c2.jpg)

De nombreux développeurs ont du mal à travailler avec des images. La gestion du [responsive](https://www.freecodecamp.org/news/css-responsive-image-tutorial/) et de l'alignement est particulièrement difficile, notamment le centrage d'une image au milieu de la page.

Dans cet article, je vais donc vous montrer quelques-unes des méthodes les plus courantes pour centrer une image verticalement et horizontalement à l'aide de différentes propriétés CSS.

J'ai déjà abordé les propriétés CSS [Position](https://www.freecodecamp.org/news/how-to-use-the-position-property-in-css-to-align-elements-d8f49c403a26/) et [Display](https://www.youtube.com/watch?v=hgoFi0fCv3w) dans mon précédent article. Si vous n'êtes pas familier avec ces propriétés, je vous recommande de les consulter avant de lire cet article.

Voici une version vidéo si vous souhaitez la consulter :

<figure class="video_container">
  <iframe width="640" height="480" src="https://www.youtube.com/embed/mwVNVxpkly0" frameborder="0" allowfullscreen="true"> </iframe>
</figure>

## Centrer une image horizontalement

Commençons par centrer une image horizontalement en utilisant 3 propriétés CSS différentes.

### Text-Align
La première façon de centrer une image horizontalement est d'utiliser la propriété `text-align`. Toutefois, cette méthode ne fonctionne que si l'image se trouve à l'intérieur d'un conteneur de niveau bloc tel qu'un `<div>` :

```html
<style>
  div {
    text-align: center;
  }
</style>

<div>
  <img src="votre-image.jpg">
</div>
```

### Margin: Auto

Une autre façon de centrer une image est d'utiliser la propriété `margin : auto` (pour left-margin et right-margin).

Cependant, l'utilisation de `margin : auto` seule ne fonctionnera pas pour les images. Si vous devez utiliser `margin : auto`, vous devez également utiliser deux propriétés supplémentaires.

La propriété margin-auto n'a pas d'effet sur les éléments de niveau ligne. Comme la balise `<img>` est un élément en ligne, nous devons d'abord la convertir en élément de niveau bloc :

```css
img {
  margin: auto;
  display: block;
}
```

Deuxièmement, nous devons également définir une largeur. Ainsi, les marges gauche et droite peuvent prendre le reste de l'espace vide et s'aligner automatiquement, ce qui fait l'affaire (sauf si nous lui donnons une largeur de 100 %) :

```css
img {
  width: 60%;
  margin: auto;
  display: block;
}
```

### Display : Flex

La troisième façon de centrer une image horizontalement est d'utiliser `display : flex`. Tout comme nous avons utilisé la propriété `text-align` pour un conteneur, nous utilisons `display : flex` pour un conteneur également.

Toutefois, l'utilisation de `display : flex` seul ne sera pas suffisante. Le conteneur doit également posséder une propriété supplémentaire appelée `justify-content` :

```css
div {
  display: flex;
  justify-content: center;
}

img {
  width: 60%;
}
```

La propriété `justify-content` fonctionne conjointement avec `display : flex`, que nous pouvons utiliser pour centrer l'image horizontalement.

Enfin, la largeur de l'image doit être inférieure à celle du conteneur, sinon elle occupera 100 % de l'espace et nous ne pourrons pas la centrer.

**Important** : la propriété `display : flex` n'est pas prise en charge par les anciennes versions des navigateurs. Voir [ici](https://caniuse.com/#search=display%20flex) pour plus de détails.

## Centrer une image verticalement

### Display : Flex
Pour l'alignement vertical, l'utilisation de `display : flex` est à nouveau très utile.

Prenons le cas où notre conteneur a une hauteur de 800 px, mais où la hauteur de l'image n'est que de 500 px :

```css
div {
  display: flex;
  justify-content: center;
  height: 800px;
}

img {
  width: 60%;
  height: 500px;
}
```

Dans ce cas, l'ajout d'une seule ligne de code au conteneur, `align-items : center`, fait l'affaire :

```css
div {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 800px;
}
```

La propriété `align-items` peut positionner les éléments verticalement si elle est utilisée conjointement avec `display : flex`.

### Position : Absolute et propriétés Transform

Une autre méthode d'alignement vertical consiste à utiliser conjointement les propriétés `position` et `transform`. Cette méthode est un peu compliquée, nous allons donc procéder étape par étape.

### Étape 1 : Définir Position Absolute

Tout d'abord, nous changeons le comportement de positionnement de l'image de `static` à `absolute` :

```css
div {
  height: 800px;
  position: relative;
  background: red;
}

img {
  width: 80%;
  position: absolute;
}
```

De plus, il doit se trouver à l'intérieur d'un conteneur positionné de manière relative, nous ajoutons donc `position : relative` à son conteneur div.

### Étape 2 : Définir les propriétés du haut et de la gauche

Ensuite, nous définissons les propriétés de haut et de gauche pour l'image, et nous les fixons à 50%. Cela déplacera le point de départ (haut-gauche) de l'image au centre du conteneur :

```css
img {
  width: 80%;
  position: absolute;
  top: 50%;
  left: 50%;
}
```

### Étape 3 : Définir la propriété de transformation

Mais la deuxième étape a déplacé l'image partiellement en dehors de son conteneur. Nous devons donc la ramener à l'intérieur.

Définir une propriété  `transform` et ajouter -50% à ses axes X et Y fait l'affaire :

```css
img {
  width: 80%;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

Il existe d'autres façons de centrer les choses horizontalement et verticalement, mais j'ai expliqué les plus courantes. J'espère que ce post vous a aidé à comprendre comment aligner vos images au centre de la page.

**Si vous voulez en savoir plus sur le développement Web, n'hésitez pas à visiter ma [chaîne Youtube](https://www.youtube.com/channel/UC1EgYPCvKCXFn8HlpoJwY3Q?view_as=subscriber) pour en savoir plus.**

Merci de votre lecture !