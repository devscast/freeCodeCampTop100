https://www.freecodecamp.org/news/how-to-center-anything-with-css-align-a-div-text-and-more/

# Comment centrer n'importe quoi avec CSS - Aligner un Div, du texte, etc.

Le centrage des objets est l'un des aspects les plus difficiles du CSS.

Les méthodes elles-mêmes ne sont généralement pas difficiles à comprendre. C'est plutôt dû au fait qu'il existe de nombreuses façons de centrer les éléments.

La méthode que vous utilisez peut varier en fonction de l'élément HTML que vous essayez de centrer, ou si vous le centrez horizontalement ou verticalement.

Dans ce tutoriel, nous allons voir comment centrer différents éléments horizontalement, verticalement, et à la fois verticalement et horizontalement.

## Comment centrer horizontalement

Centrer des éléments horizontalement est généralement plus facile que de les centrer verticalement. Voici quelques éléments courants que vous pouvez vouloir centrer horizontalement et différentes façons de le faire.

Comment centrer du texte avec la propriété CSS Text-Align Center ?
Pour centrer horizontalement du texte ou des liens, il suffit d'utiliser la propriété `text-align` avec la valeur `center` :


```html
<div class="container">
  <p>Hello, (centered) World!</p>
</div>
```

```css
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
}

p {
  /* Center horizontally*/
  text-align: center;
}
```

## Comment centrer un Div avec CSS Margin Auto

Utilisez la propriété `margin` avec la valeur `0 auto` pour centrer horizontalement des éléments de niveau bloc comme un `div` :

```html5
<div class="container">
  <div class="child"></div>
</div>
```

```css
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center horizontally*/
  margin: 0 auto;
}
```

## Comment centrer un Div horizontalement avec Flexbox

Flexbox est le moyen le plus moderne de centrer les éléments sur la page et facilite considérablement la conception de mises en page réactives. Cependant, il n'est pas entièrement pris en charge par certains anciens navigateurs comme Internet Explorer.

Pour centrer un élément horizontalement avec Flexbox, il suffit d'appliquer `display : flex` et `justify-content : center` à l'élément parent :

```html5
<div class="container">
  <div class="child"></div>
</div>
```

```css
container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Center child horizontally*/
  display: flex;
  justify-content: center;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
}
```

## Comment centrer verticalement

Centrer des éléments verticalement sans les méthodes modernes comme Flexbox peut être une véritable corvée. Nous allons d'abord passer en revue certaines des méthodes les plus anciennes pour centrer les éléments verticalement, puis nous vous montrerons comment le faire avec Flexbox.

## Comment centrer un Div verticalement avec le positionnement absolu CSS et les marges négatives ?

Pendant longtemps, cette méthode a été la plus utilisée pour centrer les objets verticalement. Pour cette méthode, vous devez connaître la hauteur de l'élément que vous souhaitez centrer.

Tout d'abord, définissez la propriété `position` de l'élément parent sur `relative`.

Ensuite, pour l'élément enfant, définissez la propriété de `position` sur `absolue` et  `top` sur `50 %`:

```html5
<div class="container">
  <div class="child"></div>
</div>
```

```css
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Setup */
  position: relative;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center vertically */
  position: absolute;
  top: 50%;
}
```

Mais cela ne fait que centrer verticalement le bord supérieur de l'élément enfant.

Pour centrer réellement l'élément enfant, définissez la propriété `margin-top` sur `-(la moitié de la hauteur de l'élément enfant)` :

```css
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Setup */
  position: relative;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center vertically */
  position: absolute;
  top: 50%;
  margin-top: -25px; /* Half this element's height */
}
```

## Comment centrer un Div verticalement avec Transform et Translate

Si vous ne connaissez pas la hauteur de l'élément que vous souhaitez centrer (ou même si vous la connaissez), cette méthode est une astuce astucieuse.

Cette méthode est très similaire à la méthode des marges négatives ci-dessus. Définissez la propriété `position` de l'élément parent sur `relative`.

Pour l'élément enfant, définissez la propriété `position` sur `absolute` et définissez top sur `50%`. Maintenant, au lieu d'utiliser une marge négative pour centrer réellement l'élément enfant, il suffit d'utiliser `transform : translate(0, -50%)` :

```html5
<div class="container">
  <div class="child"></div>
</div>
```

```css
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Setup */
  position: relative;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center vertically */
  position: absolute;
  top: 50%;
  transform: translate(0, -50%);
}
```

Notez que `translate(0, -50%)` est un raccourci pour `translateX(0)` et` translateY(-50%)`. Vous pouvez également écrire `transform : translateY(-50%)` pour centrer l'élément enfant verticalement.


## Comment centrer un Div verticalement avec Flexbox

Comme pour le centrage horizontal, Flexbox permet de centrer très facilement les éléments verticalement.

Pour centrer un élément verticalement, appliquez `display : flex` et `align-items : center` à l'élément parent :

```html5
<div class="container">
  <div class="child"></div>
</div>
```

```css
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Center vertically */
  display: flex;
  align-items: center;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
}
```


## Comment centrer un Div à la fois verticalement et horizontalement

### Comment centrer un Div verticalement et horizontalement avec le positionnement absolu CSS et les marges négatives

Cette méthode est très similaire à celle utilisée ci-dessus pour centrer un élément verticalement. Comme la dernière fois, vous devez connaître la largeur et la hauteur de l'élément que vous souhaitez centrer.

Définissez la propriété `position` de l'élément parent sur `relative`.

Définissez ensuite la propriété de `position` de l'élément enfant sur `absolut`e, `top` a `50%`, et `left` a `50%`. Cela permet de centrer le coin supérieur gauche de l'élément enfant verticalement et horizontalement.

Pour centrer réellement l'élément enfant, appliquez une marge supérieure négative définie sur la moitié de la hauteur de l'élément enfant et une marge gauche négative définie sur la moitié de la largeur de l'élément enfant :


```html5
<div class="container">
  <div class="child"></div>
</div>
```

```css
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Setup */
  position: relative;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center vertically and horizontally */
  position: absolute;
  top: 50%;
  left: 50%;
  margin: -25px 0 0 -25px; /* Apply negative top and left margins to truly center the element */
}
```

## Comment centrer un Div verticalement et horizontalement avec Transform et Translate

Utilisez cette méthode pour centrer un élément verticalement et horizontalement si vous ne connaissez pas ses dimensions exactes et ne pouvez pas utiliser Flexbox.

Tout d'abord, définissez la propriété `position` de l'élément parent sur `relative`.

Ensuite, définissez la propriété `position` de l'élément enfant sur `absolute`, `top` sur `50 %` et `left` sur `50 %`.
`
Enfin, utilisez `transform : translate(-50%, -50%)` pour centrer réellement l'élément enfant :


```html5
<div class="container">
  <div class="child"></div>
</div>
```

```css
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Setup */
  position: relative;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
  /* Center vertically and horizontally */
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

## Comment centrer un Div verticalement et horizontalement avec Flexbox

Flexbox est le moyen le plus simple de centrer un élément à la fois verticalement et horizontalement.

Il s'agit en fait d'une combinaison des deux méthodes Flexbox précédentes. Pour centrer l'élément ou les éléments enfants horizontalement et verticalement, appliquez `justify-content : center` et `align-items : center` à l'élément parent :

```html5
<div class="container">
  <div class="child"></div>
</div>
```

```css
.container {
  font-family: arial;
  font-size: 24px;
  margin: 25px;
  width: 350px;
  height: 200px;
  outline: dashed 1px black;
  /* Center vertically and horizontally */
  display: flex;
  justify-content: center;
  align-items: center;
}

.child {
  width: 50px;
  height: 50px;
  background-color: red;
}
```

C'est tout ce que vous devez savoir pour centrer avec les meilleurs d'entre eux. Maintenant, allez-y et centrez toutes les choses.