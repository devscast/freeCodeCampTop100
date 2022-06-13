# Bouton HTML onclick - Tutoriel sur les événements de clics JavaScript2021].

![img cover](https://www.freecodecamp.org/news/content/images/size/w2000/2021/08/javascript-onclick.png)

Chaque fois que vous visitez un site Web, vous cliquez probablement sur un lien ou un bouton.

Les liens vous amènent à une certaine partie de la page, à une autre page du site Web ou à un autre site Web. Les boutons, quant à eux, sont généralement manipulés par des événements JavaScript afin de pouvoir déclencher certaines fonctionnalités.

Dans ce tutoriel, nous allons explorer les deux façons différentes d'exécuter des événements de clic en JavaScript en utilisant deux méthodes différentes.

Tout d'abord, nous examinerons le style traditionnel d'onclick que vous faites directement à partir de la page HTML. Puis nous verrons comment fonctionne l'eventListner "click" plus moderne, qui vous permet de séparer le HTML du JavaScript.


# Comment utiliser l'événement onclick en JavaScript

L'événement onclick exécute une certaine fonctionnalité lorsqu'un bouton est cliqué. Cela peut être le cas lorsqu'un utilisateur soumet un formulaire, lorsque vous modifiez certains contenus sur la page Web, et d'autres choses de ce genre.

Vous placez la fonction JavaScript que vous souhaitez exécuter à l'intérieur de la balise d'ouverture du bouton.

## Syntaxe onclick de base

```html
<element onclick="functionToExecute()">Click</element>
```
Par exemple

```html
<button onclick="functionToExecute()">Click</button>
```

Notez que l'attribut onclick est purement JavaScript. La valeur qu'il prend, qui est la fonction que vous voulez exécuter, dit tout, car elle est invoquée directement dans la balise d'ouverture.

En JavaScript, vous invoquez une fonction en appelant son nom, puis vous mettez une parenthèse après l'identifiant de la fonction (le nom).

## Exemple d'événement onclick

J'ai préparé du HTML de base avec un peu de style pour que nous puissions mettre l'événement onclick en pratique.

```html
<div>
  <p class="name">freeCodeCamp</p>
  <button>Change to Blue</button>
</div>
```

Et voici la feuille de style en cascade (CSS), ainsi que tout le reste du code de l'exemple :

```css
body {
   display: flex;
   align-items: center;
   justify-content: center;
   height: 100vh;
      }
p {
   font-size: 2rem;
}

button {
    padding: 7px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button.blue {
    background-color: #3498db;
}

button.green {
    background-color: #2ecc71;
}

button.orange {
   background-color: orangered;
}
```
Donc, sur la page web, voici ce que nous avons :
![img img](https://www.freecodecamp.org/news/content/images/2021/08/changeColor.png)

Notre objectif est de changer la couleur du texte en bleu lorsque nous cliquons sur le bouton. Nous devons donc ajouter un attribut onclick à notre bouton, puis écrire la fonction JavaScript pour changer la couleur.

Nous devons donc apporter une légère modification à notre HTML :

```html
<div>
  <p class="name">freeCodeCamp</p>
  <button onclick="changeColor()">Change to Blue</button>
</div>
```
La fonction que nous voulons exécuter est changeColor(). Nous devons donc l'écrire dans un fichier JavaScript, ou dans le fichier HTML à l'intérieur d'une balise <script>.

Si vous voulez écrire votre script dans un fichier JavaScript, vous devez le lier dans le fichier HTML en utilisant la syntaxe ci-dessous :

```html
<script src="path-to-javascript-file"></script>
```
Si vous voulez écrire le script dans un fichier HTML, il suffit de le placer à l'intérieur de la balise script :

```html
<script>
  // Your Scripts
</script>
```
Maintenant, écrivons notre fonction changeColor().

Tout d'abord, nous devons sélectionner l'élément que nous voulons manipuler, qui est le texte de freeCodeCamp à l'intérieur de la balise <p>.

En JavaScript, vous faites cela avec les méthodes getElementById(), getElementsByClassName() ou querySelector() du DOM. Ensuite, vous stockez la valeur dans une variable.

Dans ce tutoriel, j'utiliserai la méthode querySelector() car elle est plus moderne et plus rapide. J'utiliserai également const pour déclarer nos variables au lieu de let et var, car avec const, les choses sont plus sûres car la variable devient en lecture seule.

```js
const name = document.querySelector(".name");
```

Maintenant que nous avons sélectionné le texte, écrivons notre fonction. En JavaScript, la syntaxe de base des fonctions ressemble à ceci :

```js
function funcctionName () {
    // What to do
} 
```
Écrivons donc notre fonction :
```js
function changeColor() {
    name.style.color = "blue";
}
```
Que se passe-t-il ?

Rappelez-vous, d'après le HTML, que changeColor() est la fonction que nous allons exécuter. C'est pourquoi notre identificateur de fonction (nom) est défini comme changeColor. Si le nom ne correspond pas à ce qui se trouve dans le code HTML, cela ne fonctionnera pas.

Dans le DOM (Document Object Model, qui fait référence à l'ensemble du HTML), pour modifier tout ce qui a trait au style, vous devez écrire "style", puis un point (.). Ce point est suivi de ce que vous voulez changer, qui peut être la couleur, la couleur de fond, la taille de la police, etc.

Ainsi, dans notre fonction, nous prenons la variable name que nous avons déclarée pour obtenir notre texte freeCodeCamp, puis nous changeons la couleur en bleu.

La couleur de notre texte devient bleue chaque fois que le bouton est cliqué :

![img img](https://www.freecodecamp.org/news/content/images/2021/08/changeColor.gif)
Notre code fonctionne !

Nous pourrions aller un peu plus loin en modifiant notre texte pour qu'il soit plus coloré :

```html
<div>
      <p class="name">freeCodeCamp</p>
      <button onclick="changeColor('blue')" class="blue">Blue</button>
      <button onclick="changeColor('green')" class="green">Green</button>
      <button onclick="changeColor('orangered')" class="orange">Orange</button>
</div>
```
Nous voulons donc changer le texte en bleu, vert et rouge-orange.

Cette fois, les fonctions onclick de notre HTML prennent les valeurs de la couleur que nous voulons donner au texte. Ces valeurs sont appelées paramètres en JavaScript. La fonction que nous allons écrire prend aussi le sien, que nous appellerons "color".

Notre page web a un peu changé :

![img img](https://www.freecodecamp.org/news/content/images/2021/08/changeColors.png)

Donc, sélectionnons notre texte freeCodeCamp et écrivons la fonction pour changer sa couleur en bleu, vert, et rouge-orange :

```js
const name = document.querySelector(".name");

function changeColor(color) {
   name.style.color = color;
}
```
Le bloc de code dans la fonction prend la variable name (où nous avons stocké notre texte freeCodeCamp), puis fixe la couleur à ce que nous avons passé dans les fonctions changeColor() dans les boutons HTML.
![img img](https://www.freecodecamp.org/news/content/images/2021/08/changeColors.gif)

## Comment utiliser l'eventListener click en JavaScript

En JavaScript, il existe plusieurs façons de faire la même chose. Comme JavaScript lui-même a évolué au fil du temps, nous avons commencé à avoir besoin de séparer le code HTML, CSS et JavaScript afin de respecter les meilleures pratiques.

Les écouteurs d'événements rendent cela possible car ils vous permettent de séparer le JavaScript du HTML. Vous pouvez également le faire avec onclick, mais nous allons adopter une autre approche.
Traduit avec www.DeepL.com/Translator (version gratuite)
Les [utilisateurs les mieux classés](https://www.topcoder.com/tc?module=AlgoRank) sur TopCoder sont de très bons programmeurs compétitifs et participent régulièrement à des concours de programmation. L'utilisateur le mieux classé tient [son propre blog](http://petr-mitrichev.blogspot.com/) intitulé _Algorithms weekly_ by Petr Mitrichev, où il écrit sur les compétitions de codage, les algorithmes, les mathématiques, etc.

### Syntaxe de base de l'eventListener

```js
element.addEventListener("type-of-event", functionToExecute)
```
Maintenant, changeons le texte freeCodeCampt en bleu en utilisant l'événement clickListner.

Voici notre nouveau HTML :

```html
 <div>
      <p class="name">freeCodeCamp</p>
      <button>Change Color</button>
 </div>
 ```
 Et voilà à quoi ça ressemble :
 ![img img](https://www.freecodecamp.org/news/content/images/2021/08/colorChange.png)
 
 colorChange

Cette fois-ci, dans notre script, nous devons aussi sélectionner le bouton (et pas seulement le texte de freeCodeCamp). C'est parce qu'il n'y a rien de JavaScript dans la balise d'ouverture de notre bouton, ce qui est cool.

Donc, notre script ressemble à ceci :
```js
const name = document.querySelector(".name");
const btn = document.querySelector("button");

      btn.addEventListener("click", function () {
        name.style.color = "blue";
 });
 ```

Nous pouvons également séparer totalement notre fonction de l'eventListener et notre fonctionnalité restera la même :

```js
btn.addEventListener("click", changeColor);
      function changeColor() {
        name.style.color = "blue";
}
```

![img img](https://www.freecodecamp.org/news/content/images/2021/08/changeColorWithEvents.gif)

### Comment construire un bouton " Show More " et " Show Less " ? avec JavaScrpit

L'une des meilleures façons d'apprendre est de réaliser des projets, alors prenons ce que nous avons appris sur les événements onclick et "click" pour construire quelque chose.

Lorsque vous visitez un blog, vous voyez souvent d'abord des extraits d'articles. Ensuite, vous pouvez cliquer sur un bouton "read more" pour afficher le reste. Essayons de faire cela.

Voici le HTML avec lequel nous travaillons :

``` html
<article id="content">
      <p>
        freeCodeCamp is one of the best platforms to learn how to code.
        freeCodeCamp has a detailed curriculum that will take you from zero to
        hero in web development, software engineering, machine learning, and
        more.
      </p>

      <p>
        freeCodeCamp also has a YouTube channel containing over 1000 videos on
        web development, software engineering, machine learning, data science,
        freelance web development, database administration, and pretty much
        anything related to tech. To get updates when videos are uploaded, you
        need to subscribe to the channel and turn on notifications. You can also
        follow freeCodeCamp on Twitter, where links to well written articles and
        videos are tweeted daily.
      </p>

      <p>
        Since no one has to pay to learn how to code on freeCodeCamp,
        freeCodeCamp runs on voluntary donations from donors all around the
        world in order to pay employees and maintain servers. If you are
        generous enough consider joining the donors.
      </p>
    </article>

<button onclick="showMore()">Show more</button>
```

C'est un simple HTML avec quelques faits sur freeCodeCamp. Et il y a un bouton auquel nous avons déjà attaché un onclick. La fonction que nous voulons exécuter est showMore(), que nous allons écrire bientôt.

Sans CSS, voici ce que nous avons :

![img img](https://www.freecodecamp.org/news/content/images/2021/08/articleunstyled.png)
Il n'est pas super moche, mais nous pouvons l'améliorer et le faire agir comme nous le souhaitons. Nous disposons donc de quelques CSS que je vais expliquer ci-dessous :

``` html
<style>
      * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
      }

      body {
        background: #f1f1f1;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
      }

      article {
        width: 400px;
        background: #fff;
        padding: 20px 20px 0;
        font-size: 18px;
        max-height: 270px;
        overflow: hidden;
        transition: max-height 1s;
        text-align: justify;
        margin-top: 20px;
      }

      p {
        margin-bottom: 16px;
      }

      article.open {
        max-height: 1000px;
      }

      button {
        background: #0e0b22;
        color: #fff;
        padding: 0.6rem;
        margin-top: 20px;
        border: none;
        border-radius: 4px;
      }

      button:hover {
        cursor: pointer;
        background: #1e1d25;
      }
</style>

```
Que fait le CSS ?

Avec le sélecteur universel (*), nous supprimons la marge et le remplissage par défaut attribués aux éléments afin de pouvoir ajouter nos propres marge et remplissage.

La taille de la boîte est également définie sur border-box afin que nous puissions inclure le remplissage et la bordure dans la largeur et la hauteur totales de nos éléments.

Nous avons centré tout ce qui se trouve dans le corps avec Flexbox et lui avons donné un fond gris clair.

Notre élément <article>, qui contient le texte, a une largeur de 400px, un arrière-plan blanc (#fff) et un remplissage de 20px en haut, 20 à gauche et à droite, et 0 en bas.

Les balises de paragraphe qu'il contient ont une taille de police de 18px, et nous leur avons donné une hauteur maximale de 270px. En raison de la hauteur maximale de l'élément article, tout le texte ne sera pas contenu et débordera. Pour remédier à ce problème, nous avons défini le paramètre overflow sur hidden afin de ne pas afficher le texte dans un premier temps.

La propriété de transition garantit que chaque changement se produit après 1 seconde. Tous les textes contenus dans l'article sont justifiés et ont une marge supérieure de 20 pixels afin qu'ils ne restent pas trop attachés au haut de la page.

Comme nous avons supprimé la marge par défaut, nos paragraphes ont été poussés les uns contre les autres. Nous avons donc défini une marge inférieure de 16 pixels afin de les séparer les uns des autres.

Notre sélecteur, article.open, a une propriété de max-height fixée à 1000px. Cela signifie qu'à chaque fois que l'élément article est associé à une classe open, la hauteur maximale passe de 270 à 1000 pixels pour afficher le reste de l'article. C'est possible grâce à JavaScript, qui change la donne.

Nous avons stylisé notre bouton avec un fond sombre et l'avons rendu blanc. Nous avons défini sa bordure sur none pour supprimer la bordure par défaut du HTML sur les boutons, et nous lui avons donné un rayon de bordure de 4px pour qu'il ait une bordure légèrement arrondie.

Enfin, nous avons utilisé la pseudo-classe de survol en CSS pour transformer le curseur du bouton en pointeur. La couleur de l'arrière-plan change légèrement lorsqu'un utilisateur passe son curseur dessus.

Voilà, c'est le CSS.

Notre page est maintenant plus belle :

![img img](https://www.freecodecamp.org/news/content/images/2021/08/articlestyled.png)
La prochaine chose à faire est d'écrire notre JavaScript pour que nous puissions voir le reste de l'article qui est caché.

Nous avons un attribut onclick à l'intérieur de notre balise d'ouverture de bouton, prêt à exécuter une fonction showMore(), alors écrivons la fonction.

Nous devons d'abord sélectionner notre article, car nous devons afficher le reste de l'article :

```js
const article = document.querySelector("#content");
```
La prochaine chose à faire est d'écrire la fonction showMore() afin de pouvoir basculer entre l'affichage du reste de l'article et son masquage.

```js
function showMore() {
     if (article.className == "open") {
       // read less
       article.className = "";
       button.innerHTML = "Show more";
     } else {
       //read more
       article.className = "open";
       button.innerHTML = "Show less";
     }
  }
```

Que fait la fonction ?

Nous utilisons ici une instruction if...else. Il s'agit d'une partie cruciale de JavaScript qui vous aide à prendre des décisions dans votre code si une certaine condition est remplie.

La syntaxe de base ressemble à ceci :

```js


if (condition == "something") {
  // Do something
} else {
  // Do something else
}

```
Ici, si le nom de classe de l'article est égal à open (c'est-à-dire que nous voulons lui ajouter la classe open, qui a été définie pour une hauteur maximale de 1000px dans le CSS), alors nous voulons voir le reste de l'article. Sinon, nous voulons que l'article revienne à l'état initial où une partie de celui-ci est cachée.

Pour ce faire, nous lui attribuons la classe open dans le bloc else, ce qui lui permet d'afficher le reste de l'article. Ensuite, nous attribuons à la classe une chaîne vide (none) dans le bloc if, ce qui la fait revenir à l'état initial.

Notre code fonctionne bien avec une transition en douceur :

![img img](https://www.freecodecamp.org/news/content/images/2021/08/article.gif)

Nous pouvons séparer le HTML et le JavaScript et continuer à utiliser onclick, car onclick est du JavaScript. Il est donc possible d'écrire ceci dans un fichier JavaScript au lieu de partir du HTML.

```js
 button.onclick = function () {
     if (article.className == "open") {
       // read less
       article.className = "";
       button.innerHTML = "Show more";
     } else {
       //read more
       article.className = "open";
       button.innerHTML = "Show less";
     }
  };
 ```
 ![img img](https://www.freecodecamp.org/news/content/images/2021/08/articleonclick.gif)
 
 Nous pouvons également le faire en utilisant un EventListner :
 
 ```html
 <article id="content">
      <p>
        freeCodeCamp is one of the best platforms to learn how to code.
        freeCodeCamp has a detailed curriculum that will take you from zero to
        hero in web development, software engineering, machine learning, and
        many more.
      </p>

      <p>
        freeCodeCamp also has a YouTube channel containing over 1000 videos on
        web development, software engineering, machine learning, data science,
        freelance web development, database administration, and pretty more
        anything related to tech. To get updates when videos are uploaded, you
        need to subscribe to the channel and turn on notifications. You can also
        follow freeCodeCamp on Twitter, where links to well written articles and
        videos are tweeted daily.
      </p>

      <p>
        Since no one has to pay to learn how to code on freeCodeCamp,
        freeCodeCamp runs on voluntary donations from donors all around the
        world in order to pay employees and maintain servers. If you are
        generous enough consider joining the donors.
      </p>
</article>

<button id="read-more">Show more</button>
```
```js
 const article = document.querySelector("#content");
 const button = document.querySelector("#read-more");

button.addEventListener("click", readMore);

function readMore() {
     if (article.className == "open") {
       // Read less
     article.className = "";
     button.innerHTML = "Show more";
   } else {
     article.className = "open";
     button.innerHTML = "Show less";
   }
}
```
Notre fonctionnalité reste la même !
### Conclusion

J'espère que ce tutoriel vous aidera à comprendre le fonctionnement de l'événement de clic en JavaScript. Nous avons exploré deux méthodes différentes ici, donc maintenant vous pouvez commencer à les utiliser dans vos projets de codage.

Merci de votre lecture, et continuez à coder.


