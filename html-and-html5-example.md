https://www.freecodecamp.org/news/html-and-html5-example/

# Les meilleurs exemples HTML et HTML5

Le langage HTML fournit la structure des sites Web. Voici quelques exemples de la façon d'utiliser la syntaxe HTML pour construire des sites Web, y compris quelques exemples des nouvelles fonctionnalités de HTML5.

## L'exemple de l'attribut Href
L'attribut `<a href>` fait référence à une destination fournie par un lien. La balise `a` (ancre) est morte sans l'attribut `<href>`. Parfois, dans votre flux de travail, vous ne voulez pas de lien vivant ou vous ne connaîtrez pas encore la destination du lien. Dans ce cas, il est utile de définir l'attribut `href` sur `"#"` pour créer un lien mort. L'attribut `href` peut être utilisé pour créer un lien vers des fichiers locaux ou des fichiers sur Internet.

Par exemple :

```html
<html>
  <head>
    <title>Href Attribute Example</title>
  </head>
  <body>
    <h1>Href Attribute Example</h1>
    <p>
      <a href="https://www.freecodecamp.org/contribute/">The freeCodeCamp Contribution Page</a> shows you how and where you can contribute to freeCodeCamp's community and growth.
    </p>
  </body>
</html>
```
L'attribut `<a href>` est pris en charge par tous les navigateurs.

## Autres attributs :

`hreflang `: Spécifie la langue de la ressource liée. `target` : Spécifie le contexte dans lequel la ressource liée s'ouvrira. `title` : Définit le titre d'un lien, qui apparaît à l'utilisateur sous forme d'infobulle.

Examples

```html
<a href="#">This is a dead link</a>
<a href="https://www.freecodecamp.org">This is a live link to freeCodeCamp</a>
<a href="https://html.com/attributes/a-href/">more with a href attribute</a>
```

Ancres dans la page
Il est également possible de définir une ancre à un endroit précis de la page. Pour ce faire, vous devez d'abord placer un onglet à un endroit de la page avec une balise et [l'attribut nécessaire "name" avec la description d'un mot-clé, comme ceci]():

```html
<a name="top"></a>
```

[Une description entre les balises n'est pas nécessaire. Ensuite, vous pouvez placer un lien menant à cette ancre à n'importe quel endroit de la même page. Pour ce faire, vous devez utiliser une balise avec l'attribut nécessaire "href" avec le symbole # (dièse) et le mot-clé de description de l'ancre, comme ceci :]()

```html
<a href="#top">Go to Top</a>
```

## Liens d'image

La balise `<a href="#">` peut également être appliquée aux images et autres éléments HTML.

Exemple

```html
<a href="#">
  <img itemprop="image" style="height: 90px;" src="https://bit.ly/fcc-relaxing-cat" alt="A cute orange cat lying on its back.">
</a>
```

#### Exemple

### L'exemple de la cible A

L'attribut `<a target>` indique où ouvrir le document lié dans une balise `a` (ancre).

#### Exemples :

Un attribut cible ayant pour valeur "_blank" ouvre le document lié dans une nouvelle fenêtre ou un nouvel onglet.


```html
<a href="https://www.freecodecamp.org/" target="_blank">freeCodeCamp</a>
```

Un attribut cible ayant la valeur "_self" ouvre le document lié dans le même cadre que celui dans lequel il a été cliqué (il s'agit de la valeur par défaut et il n'est généralement pas nécessaire de la spécifier).

```html
<a href="https://www.freecodecamp.org/" target="_self">freeCodeCamp</a>
```

```html
<a href="https://www.freecodecamp.org/">freeCodeCamp</a>
```

Un attribut cible ayant la valeur "_parent" ouvre le document lié dans le cadre parent.

```html
<a href="https://www.freecodecamp.org/" target="_parent">freeCodeCamp</a>
```

Un attribut cible ayant la valeur "_top" ouvre le document lié dans le corps complet de la fenêtre.

```html
<a href="https://www.freecodecamp.org/" target="_top">freeCodeCamp</a>
```

Un attribut cible avec la valeur "framename" ouvre le document lié dans un cadre nommé spécifié.

```html
<a href="https://www.freecodecamp.org/" target="framename">freeCodeCamp</a>
```

## Exemple de l'attribut d'arrière-plan du corps

Si vous souhaitez ajouter une image d'arrière-plan au lieu d'une couleur, une solution est l'attribut `<body background>`. Il spécifie une image d'arrière-plan pour un document HTML.

Syntaxe :

`<body background="URL">`

Attribut :

`background - URL de l'image d'arrière-plan`

Exemple :

```html
<html>
  <body background="https://assets.digitalocean.com/blog/static/hacktoberfest-is-back/hero.png">
  </body>
</html>
```

### l'attribut body-background est déprécié

l'attribut body-background a été déprécié en HTML5. La façon correcte de styliser la balise `<body>` est avec CSS.

Il existe plusieurs propriétés CSS utilisées pour définir l'arrière-plan d'un élément. Elles peuvent être utilisées pour définir l'arrière-plan d'une page entière.

### Exemple de l'attribut body bgcolor

L'attribut `<body bgcolor>` attribue une couleur d'arrière-plan à un document HTML.

Syntaxe :

`<body bgcolor="color">` La valeur de la couleur peut être soit un nom de couleur (comme, `purple`), soit une valeur hexadécimale (comme, `#af0000`).

Pour ajouter une couleur de fond à une page Web, vous pouvez utiliser l'attribut `<body bgcolor="######">`. Il spécifie une couleur à afficher dans le document HTML.

Par exemple :

```html
<html>
  <head>
    <title>Body bgcolor Attribute example</title>
  </head>
  <body bgcolor="#afafaf">
    <h1>This webpage has colored background.</h1>
  </body>
</html>
```

Vous pouvez changer la couleur en remplaçant ###### par une valeur hexadécimale. Pour les couleurs simples, vous pouvez également utiliser le mot, comme "rouge" ou "noir".

Tous les principaux navigateurs prennent en charge l'attribut `<body bgcolor>`.

Remarque :

* HTML 5 ne prend pas en charge l'attribut `<body bgcolor>`. Utilisez le CSS à cette fin. Comment ? En utilisant le code suivant : `<body style="background-color : color">` Bien sûr, vous pouvez également le faire dans un document séparé au lieu d'une méthode en ligne.
* N'utilisez pas la valeur RGB dans l'attribut `<body bgcolor>` car rgb() est uniquement pour CSS, c'est-à-dire qu'il ne fonctionnera pas en HTML.

## Exemple de l'attribut Div Align

L'attribut `<div align="">` est utilisé pour aligner le texte d'une balise div à gauche, à droite, au centre ou en le justifiant.

Par exemple :

```html
<html>
  <head>
    <title>Div Align Attribbute</title>
  </head>
  <body>
    <div align="left">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
      labore et dolore magna aliqua.
    </div>
    <div align="right">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
      labore et dolore magna aliqua.
    </div>
    <div align="center">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
      labore et dolore magna aliqua.
    </div>
    <div align="justify">
      Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
      labore et dolore magna aliqua.
    </div>
  </body>
</html>
```
### Important !

Cet attribut n'est plus pris en charge par HTML5. Il faut utiliser le langage css.

L'attribut Div Align peut être utilisé pour aligner horizontalement le contenu d'un div. Dans l'exemple ci-dessous, le texte sera centré dans la division.

```html
<div align="center">
  This Text Will Be Centered
</div>
```

Cet attribut n'est pas pris en charge par HTML5 et il convient d'utiliser l'option CSS Text Align à la place.

### Exemple d'attribut de couleur de police

Cet attribut est utilisé pour définir une couleur pour le texte enfermé dans une balise `<font>`.

Important:
Cet attribut n'est pas pris en charge dans HTML5. Au lieu de cela, cet [article freeCodeCamp](https://www.freecodecamp.org/news/the-css-handbook-a-handy-guide-to-css-for-developers-b56695917d11/#colors) spécifie une méthode CSS, qui peut être utilisée.

#### Noter:

Une couleur peut également être spécifiée à l'aide d'un 'code hexadécimal' ou d'un 'code rvb', au lieu d'utiliser un nom.

Exemple:

1. Attribut de nom de couleur

```html
<html>
  <body>
    <font color="green">Font color example using color attribute</font>
  </body>
</html>
```

Attribut du code hexadécimal

```html
<html>
  <body>
    <font color="#00FF00">Font color example using color attribute</font>
  </body>
</html>
```
Attribut RVB

```html
<html>
  <body>
    <font color="rgb(0,255,0)">Font color example using color attribute</font>
  </body>
</html>
```

## Exemple de l'attribut Taille de la police

Cet attribut spécifie la taille de la police sous forme de valeur numérique ou relative. Les valeurs numériques vont de `1` à `7`, `1` étant la plus petite et `3` la valeur par défaut. Elle peut également être définie à l'aide d'une valeur relative, comme `+2` ou `-3`, qui la définit par rapport à la valeur de l'attribut size de l'élément `<basefont>`, ou par rapport à `3`, la valeur par défaut, s'il n'en existe pas.

Syntaxe :

`<font size="nombre">`

Exemple :

```html
<html>
  <body>
    <font size="6">This is some text!</font>
  </body>
</html>
```

Note : `L'attribut size de <font> n'est pas supporté en HTML5. Utilisez le CSS à la place.`

### Exemple de l'attribut Align d'une image

L'attribut align d'une image indique où l'image doit être alignée par rapport à l'élément qui l'entoure.

Valeurs de l'attribut :
right - Aligne l'image sur la droite left - Aligne l'image sur la gauche
top - Aligne l'image en haut
bottom - Aligne l'image sur le bas
middle - Aligne l'image au milieu

Par exemple :

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Img Align Attribute</title>
  </head>
  <body>
    <p>
      This is an example. <img src="image.png" alt="Image" align="middle" /> More text right here
      <img src="image.png" alt="Image" width="100" />
    </p>
  </body>
</html>
```

On peut aussi s'aligner à droite si on veut :

```html
<p>This is another example<img src="image.png" alt="Image" align="right" /></p>
```
Veuillez noter que l'attribut align n'est pas pris en charge par HTML5 et que vous devez utiliser CSS à la place. Cependant, il est toujours pris en charge par tous les principaux navigateurs.

### L'attribut Img Width

L'attribut HTML "width" fait référence à la largeur d'une image. La valeur entre guillemets correspond au nombre de pixels.

Par exemple, si vous avez déjà établi un lien vers une image via l'attribut `src`, vous pouvez ajouter l'attribut width comme suit :

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Img Width Attribute</title>
  </head>
  <body>
    <img src="image.png" alt="Image" width="100" />
  </body>
</html>
```
Dans l'extrait de code ci-dessus, il y a une balise image et l'image est définie à une largeur de 100 pixels. `width="100"`

### Exemple de l'attribut Img Src

L'attribut `<img src>` fait référence à la source de l'image que vous souhaitez afficher. La balise `img` n'affichera pas une image sans l'attribut `src`. Cependant, si vous définissez la source à l'emplacement de l'image, vous pouvez afficher n'importe quelle image.

Il existe une image du logo de freeCodeCamp située à l'adresse `https://avatars0.githubusercontent.com/u/9892522?v=4&s=400`.

Vous pouvez la définir comme image à l'aide de l'attribut `src`.

```html
<html>
  <head>
    <title>Img Src Attribute Example</title>
  </head>
  <body>
    <img src="https://avatars0.githubusercontent.com/u/9892522?v=4&s=400" />
  </body>
</html>
```

Le code ci-dessus s'affiche comme suit :

L'attribut `src` est pris en charge par tous les navigateurs.

Vous pouvez également avoir un fichier hébergé localement comme image.

Par exemple, `<img src="images/freeCodeCamp.jpeg />` fonctionnerait si vous aviez un dossier appelé `images` contenant le fichier `freeCodeCamp.jpeg`, pour autant que le dossier 'images' se trouve au même endroit que le fichier `index.html`.

`../files/index.html`

`..fichiers/images/freeCodeCamp.jpeg`

## Aperçu

### Que sont les entités HTML ?

Les entités HTML sont des caractères utilisés pour remplacer les caractères réservés en HTML ou les caractères qui n'apparaissent pas sur votre clavier. Certains caractères sont réservés en HTML. Si vous utilisez les signes moins que (<) ou plus que (>) dans votre texte, le navigateur peut les confondre avec des balises.

### A quoi servent-elles ?

Comme mentionné à propos des entités HTML, elles sont utilisées afin de remplacer les caractères réservés par le HTML.

### Comment les utiliser ?

Une entité de caractère ressemble à ceci :

```
<!-- format &[entity_name]; -->
<!-- example for a less-than sign (<) -->
&lt;
```
ou 
```
<!-- &#[entity_number]; -->
<!-- example for a less-than sign (<) -->
&#60;
```
### Guide de référence

Il ne s'agit en aucun cas d'une liste exhaustive mais les liens ci-dessous pourront vous donner plus d'entités si celles-ci ne répondent pas à vos besoins. Bon codage :bowtie :

```
Character	Entity Name	Entity Number	Description
&#32;	Space
!		&#33;	Exclamation mark
”		&#34;	Quotation mark
#		&#35;	Number sign
$		&#36;	Dollar sign
¢	&cent;	&#162;	Cent sign
€	&euro;	&#8364;	Euro sign
£	&pound;	&#163;	GBP sign
¥	&yen;	&#165;	Yen sign
%		&#37;	Percent sign
&	&amp;	&#38;	Ampersand
’		&#39;	Apostrophe
(		&#40;	Opening/Left Parenthesis
)		&#41;	Closing/Right Parenthesis
*		&#42;	Asterisk
+		&#43;	Plus sign
,		&#44;	Comma
-		&#45;	Hyphen
.		&#46;	Period
/		&#47;	Slash
©	&copy;	&#169;	Copyright
®	&reg;	&#174;	Registered Trademark
”	&quot;	&#34;	double quotation mark
>	&gt;	&#62;	Greater-than sign
<	&lt;	&#60;	Less-than sign
•	&bull;	&#8226	Bullet point
```

### Exemple de formulaire HTML

En principe, les formulaires sont utilisés pour collecter les données saisies par un utilisateur, qui sont ensuite envoyées au serveur pour un traitement ultérieur. Ils peuvent être utilisés pour différents types d'entrées utilisateur, comme le nom, l'email, etc.

Le formulaire contient des éléments de contrôle qui sont enveloppés autour des balises `<form></form>`, comme l'entrée, qui peut avoir des types comme :

- text
- email
- password
- checkbox
- radio
- submit
- range
- search
- date
- time
- week
- color
- datalist


Code d'exemple 

```html
<form>
  <label for="username">Username:</label>
  <input type="text" name="username" id="username" />
  <label for="password">Password:</label>
  <input type="password" name="password" id="password" />
  <input type="radio" name="gender" value="male" />Male<br />
  <input type="radio" name="gender" value="female" />Female<br />
  <input type="radio" name="gender" value="other" />Other
  <input list="Options" />
  <datalist id="Options">
    <option value="Option1"></option>
    <option value="Option2"></option>
    <option value="Option3"></option>
  </datalist>

  <input type="submit" value="Submit" />
  <input type="color" />
  <input type="checkbox" name="correct" value="correct" />Correct
</form>
```

Autres éléments que le formulaire peut contenir :

- `textare` - Il s'agit d'une zone multiligne qui est le plus souvent utilisée pour ajouter du texte, par exemple un commentaire. La taille de la zone de texte est définie par le nombre de lignes et de colonnes.
- `select` - avec la balise `<option></option>`, il crée un menu déroulant de sélection.
- `button` - L'élément button peut être utilisé pour définir un bouton cliquable.

PLUS D'INFORMATIONS SUR LES FORMULAIRES HTML.

Les formulaires HTML sont nécessaires lorsque vous souhaitez recueillir certaines données auprès du visiteur du site. Par exemple, lors de l'enregistrement d'un utilisateur, vous souhaitez recueillir des informations telles que le nom, l'adresse électronique, la carte de crédit, etc.

Un formulaire prend les données du visiteur du site et les envoie à une application dorsale telle qu'un CGI, un script ASP ou un script PHP, etc. L'application dorsale effectuera le traitement requis sur les données transmises en fonction de la logique commerciale définie dans l'application.

Il existe différents éléments de formulaire tels que les champs de texte, les champs de zone de texte, les menus déroulants, les boutons radio, les cases à cocher, etc.

La balise HTML `<form>` est utilisée pour créer un formulaire HTML et a la syntaxe suivante -


```html
<form action="Script URL" method="GET|POST">form elements like input, textarea etc.</form>
```

Si la méthode du formulaire n'est pas définie, la valeur par défaut est "GET".

La balise de formulaire peut également comporter un attribut appelé "target", qui indique où le lien s'ouvrira. Il peut s'ouvrir dans un onglet du navigateur, dans un cadre ou dans la fenêtre actuelle.

L'attribut "action" définit l'action à effectuer lorsque le formulaire est soumis. Normalement, les données du formulaire sont envoyées à une page Web à l'URL du script lorsque l'utilisateur clique sur le bouton d'envoi. Si l'attribut action est omis, l'action est définie sur la page actuelle.

### Exemple d'audio HTML5

Avant HTML5, les fichiers audio devaient être lus dans un navigateur à l'aide d'un plug-in comme Adobe Flash. Le HTML

L'extrait de code suivant ajoute un fichier audio portant le nom de fichier `tutorial.ogg` ou `tutorial.mp3`. L'élémente indique des fichiers audio alternatifs parmi lesquels le navigateur peut choisir. Le navigateur utilisera le premier format reconnu.

Exemple 1

```html
<audio controls>
  <source src="tutorial.ogg" type="audio/ogg" />
  <source src="tutorial.mp3" type="audio/mpeg" />
  Your browser does not support the audio element.
</audio>
```

Exemple 2 

```html 
<audio src="https://s3.amazonaws.com/freecodecamp/simonSound1.mp3" controls loop autoplay></audio>
```

L'attribut `controls` comprend des commandes audio telles que play, pause et volume. Si vous n'utilisez pas cet attribut, aucun contrôle ne sera affiché.

L'élément `<source>` vous permet d'indiquer des fichiers audio alternatifs parmi lesquels le navigateur peut choisir. Le navigateur utilisera le premier format reconnu. Le texte entre les balises `<audio>` et <`/audio>` peut être affiché dans un navigateur qui ne prend pas en charge l'élément HTML5 `<audio>`.

L'attribut autoplay permettra de lire automatiquement votre fichier audio en arrière-plan. Il est considéré comme une meilleure pratique de laisser les visiteurs choisir la lecture de l'audio.

L'attribut preload indique ce que le navigateur doit faire si le lecteur n'est pas réglé sur autoplay.

L'attribut loop permet de lire votre fichier audio en boucle si cela est indiqué.

Comme il s'agit de html5, certains navigateurs ne le supportent pas. Vous pouvez le vérifier sur https://caniuse.com/#search=audio


## Exemple d'éléments sémantiques HTML5

Les éléments HTML sémantiques décrivent clairement sa signification d'une manière lisible par l'homme et la machine. Des éléments tels que `<header>`, `<footer>` et `<article>` sont tous considérés comme sémantiques car ils décrivent avec précision l'objectif de l'élément et le type de contenu qui s'y trouve.

## Une histoire rapide

HTML a été créé à l'origine en tant que langage de balisage pour décrire des documents sur Internet. Au fur et à mesure qu'Internet s'est développé et a été adopté par de plus en plus de personnes, ses besoins ont changé. Alors qu'Internet était à l'origine destiné au partage de documents scientifiques, les gens voulaient désormais partager d'autres choses également. Très rapidement, les gens ont commencé à vouloir rendre le Web plus agréable. Étant donné que le Web n'a pas été initialement conçu pour être conçu, les programmeurs ont utilisé différents hacks pour organiser les choses de différentes manières. Plutôt que d'utiliser le `<table></table>` pour décrire des informations à l'aide d'un tableau, les programmeurs les utiliseraient pour positionner d'autres éléments sur une page. Au fur et à mesure que l'utilisation de mises en page conçues visuellement progressait, les programmeurs ont commencé à utiliser une balise générique "non sémantique" comme `<div>`. Ils donnaient souvent à ces éléments un attribut class ou id pour décrire leur objectif. Par exemple, au lieu de `<header>` cela était souvent écrit comme `<div class="header">`. Comme HTML5 est encore relativement nouveau, cette utilisation d'éléments non sémantiques est encore très courante sur les sites Web aujourd'hui.

### Liste des nouveaux éléments sémantiques

Les éléments sémantiques ajoutés dans HTML5 sont :


- `<article>`
- `<aside>`
- `<details>`
- `<figcaption>`
- `<figure>`
- `<footer>`
- `<header>`
- `<main>`
- `<mark>`
- `<nav>`
- `<section>`
- `<summary>`
- `<time>`

Des éléments tels que <header>, <nav>, <section>, <article>, <aside> et <footer> agissent plus ou moins comme des éléments <div>. Ils regroupent d'autres éléments dans des sections de page. Cependant, là où une balise <div> peut contenir n'importe quel type d'information, il est facile d'identifier le type d'information qui irait dans une région sémantique <header>.

Un exemple de mise en page d'éléments sémantiques par w3schools


### Avantages des éléments sémantiques

Pour voir les avantages des éléments sémantiques, voici deux morceaux de code HTML. Ce premier bloc de code utilise des éléments sémantiques :

```html
<header></header>
<section>
  <article>
    <figure>
      <img />
      <figcaption></figcaption>
    </figure>
  </article>
</section>
<footer></footer>
```
Alors que ce deuxième bloc de code utilise des éléments non sémantiques :

```html
<div id="header"></div>
<div class="section">
  <div class="article">
    <div class="figure">
      <img />
      <div class="figcaption"></div>
    </div>
  </div>
</div>
<div id="footer"></div>
```

Tout d'abord, il est beaucoup plus facile à lire. C'est probablement la première chose que vous remarquerez en regardant le premier bloc de code utilisant des éléments sémantiques. Ceci est un petit exemple, mais en tant que programmeur, vous pouvez lire des centaines ou des milliers de lignes de code. Plus il est facile de lire et de comprendre ce code, plus il facilite votre travail.

Il a une plus grande accessibilité. Vous n'êtes pas le seul à trouver les éléments sémantiques plus faciles à comprendre. Les moteurs de recherche et les technologies d'assistance (comme les lecteurs d'écran pour les utilisateurs malvoyants) sont également capables de mieux comprendre le contexte et le contenu de votre site Web, ce qui signifie une meilleure expérience pour vos utilisateurs.

Dans l'ensemble, les éléments sémantiques conduisent également à un code plus cohérent. Lors de la création d'un en-tête à l'aide d'éléments non sémantiques, différents programmeurs peuvent l'écrire sous la forme <div class="header">, <div id="header">, <div class="head"> ou simplement <div>. Il existe de nombreuses façons de créer un élément d'en-tête, et elles dépendent toutes des préférences personnelles du programmeur. En créant un élément sémantique standard, cela facilite la tâche de tous.

Depuis octobre 2014, HTML4 a été mis à niveau vers HTML5, avec quelques nouveaux éléments "sémantiques". À ce jour, certains d'entre nous pourraient encore être confus quant à la raison pour laquelle tant d'éléments différents ne semblent pas montrer de changements majeurs.

### `<section>` et `<article>`

"Quelle est la différence?", Vous pouvez demander. Ces deux éléments sont utilisés pour sectionner un contenu, et oui, ils peuvent certainement être utilisés de manière interchangeable. C'est une question de dans quelle situation. HTML4 n'offrait qu'un seul type d'élément conteneur, qui est `<div>`. Bien que cela soit toujours utilisé dans HTML5, HTML5 nous a fourni `<section>` et `<article>` de manière à remplacer `<div>`.

Les éléments `<section>` et `<article>` sont conceptuellement similaires et interchangeables. Pour décider lequel de ceux-ci vous devriez choisir, prenez note de ce qui suit :

1. Un article est destiné à être indépendamment distribuable ou réutilisable.
2. Une section est un regroupement thématique de contenu.

```html 
section>
  <p>Top Stories</p>
  <section>
    <p>News</p>
    <article>Story 1</article>
    <article>Story 2</article>
    <article>Story 3</article>
  </section>
  <section>
    <p>Sport</p>
    <article>Story 1</article>
    <article>Story 2</article>
    <article>Story 3</article>
  </section>
</section>
```

### `<header>` et `<hgroup>`
L'élément `<header>` se trouve généralement en haut d'un document, d'une section ou d'un article et contient habituellement le titre principal et certains outils de navigation et de recherche.

```html 
<header>
  <h1>Company A</h1>
  <ul>
    <li><a href="/home">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact us</a></li>
  </ul>
  <form target="/search">
    <input name="q" type="search" />
    <input type="submit" />
  </form>
</header>
```

L'élément `<hgroup>` doit être utilisé lorsque vous souhaitez un titre principal avec un ou plusieurs sous-titres.

```html
<hgroup>
  <h1>Heading 1</h1>
  <h2>Subheading 1</h2>
  <h2>Subheading 2</h2>
</hgroup>
```

RAPPEL : l'élément `<header>` peut contenir n'importe quel contenu, mais l'élément `<hgroup>` ne peut contenir que d'autres en-têtes, c'est-à-dire de `<h1>` à `<h6>` en incluant `<hgroup>`.

## `<aside>`

L'élément `<aside>` est destiné à un contenu qui ne fait pas partie du flux du texte dans lequel il apparaît, mais qui reste néanmoins lié d'une certaine manière. Cette de `<aside>` comme une barre latérale à votre contenu principal.


```html
<aside>
  <p>
    This is a sidebar, for example a terminology definition or a short background to a historical
    figure.
  </p>
</aside>
```

Avant HTML5, nos menus étaient créés avec des `<ul>` et des `<li>`. Maintenant, avec ceux-ci, nous pouvons séparer nos éléments de menu avec un `<nav>`, pour la navigation entre vos pages. Vous pouvez avoir un nombre quelconque d'éléments `<nav>` sur une page, par exemple, il est courant d'avoir une navigation globale en haut (dans le `<header>`) et une navigation locale dans une barre latérale (dans un élément `<aside>`).

```html
<nav>
  <ul>
    <li><a href="/home">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact us</a></li>
  </ul>
</nav>
```

## `<footer>`

S'il y a un `<header>`, il doit y avoir un `<footer>`. Un `<footer>` se trouve généralement au bas d'un document, d'une section ou d'un article. Tout comme le `<header>`, le contenu est généralement constitué de méta-informations, telles que des détails sur l'auteur, des informations juridiques et/ou des liens vers des informations connexes. Il est également valable d'inclure des éléments `<section>` dans un pied de page.

```html
<footer>&copy;Company A</footer>
```

## `<small>`

L'élément `<small>` apparaît souvent dans un élément `<footer>` ou `<aside>` qui contient généralement des informations sur les droits d'auteur ou des clauses de non-responsabilité, et d'autres éléments de ce type. Cependant, cela ne vise pas à réduire la taille du texte. Il ne s'agit que de décrire son contenu et non de prescrire sa présentation.

```html
<footer><small>&copy;Company A</small> Date</footer>
```

## `<time>`

L'élément `<time>` permet d'associer une date ISO 8601 sans ambiguïté à une version lisible par l'homme de cette date.

```html
<time datetime="2017-10-31T11:21:00+02:00">Tuesday, 31 October 2017</time>
```

Pourquoi s'embêter avec `<time>` ? Alors que les humains peuvent lire l'heure qui peut lever l'ambiguïté grâce au contexte de manière normale, les ordinateurs peuvent lire la date ISO 8601 et voir la date, l'heure et le fuseau horaire.

## `<figure>` et `<figcaption>`

`<figure>` sert à envelopper le contenu de votre image autour d'elle, et `<figcaption>` sert à légender votre image.

```html
<figure>
  <img src="https://en.wikipedia.org/wiki/File:Shadow_of_Mordor_cover_art.jpg" alt="Shadow of Mordor" />
  <figcaption>Cover art for Middle-earth: Shadow of Mordor</figcaption>
</figure>
```

## Exemple de vidéo HTML5

Avant HTML5, pour qu'une vidéo soit lue dans une page Web, il fallait utiliser un plugin, comme Adobe Flash Player. Avec l'introduction de HTML5, vous pouvez désormais la placer directement dans la page elle-même. Le HTML

Pour intégrer un fichier vidéo dans une page Web, il suffit d'ajouter cet extrait de code et de modifier le src du fichier audio.

```html
video controls>
  <source src="tutorial.ogg" type="video /ogg" />
  <source src="tutorial.mp4" type="video /mpeg" />
  Your browser does not support the video element. Kindly,update it to latest version.
</video>
```

L'attribut controls comprend des commandes vidéo, similaires à celles de lecture, de pause et de volume.

Cette fonctionnalité est prise en charge par tous les navigateurs modernes/mis à jour. Cependant, tous ne prennent pas en charge le même format de fichier vidéo. Pour une compatibilité étendue, je recommande le format MP4, car il est le plus largement accepté. Il existe également deux autres formats (WebM et Ogg) qui sont pris en charge par Chrome, Firefox et Opera.

L'élément vous permet d'indiquer des fichiers vidéo alternatifs parmi lesquels le navigateur peut choisir. Le navigateur utilisera le premier format reconnu. En HTML5, il existe 3 formats vidéo pris en charge : MP4, WebM et Ogg.

Le texte entre les balises ne sera affiché que dans les navigateurs qui ne prennent pas en charge le format MP4.

Il y a plusieurs éléments différents dans la balise vidéo, beaucoup de ces explications sont basées sur les docs web de Mozilla (lien ci-dessous). Il y en a encore plus si vous cliquez sur le lien en bas de page.


### autoplay

L'option "autoplay" peut être définie comme vraie ou fausse. Vous le définissez comme vrai en l'ajoutant dans la balise, s'il n'est pas présent dans la balise, il est défini comme faux. S'il est défini sur true (vrai), la lecture de la vidéo commencera dès qu'une partie suffisante de la vidéo aura été mise en mémoire tampon pour pouvoir être lue. De nombreuses personnes considèrent que les vidéos en lecture automatique sont perturbantes ou ennuyeuses, alors utilisez cette fonction avec parcimonie. Notez également que certains navigateurs mobiles, tels que Safari pour iOS, ignorent cet attribut.

```html
<video autoplay>
  <source src="video.mp4" type="video/mp4" />
</video>
```

### poster

L'attribut "poster" est l'image qui s'affiche sur la vidéo jusqu'à ce que l'utilisateur clique pour la lire.

```html
<video poster="poster.png">
  <source src="video.mp4" type="video/mp4" />
</video>
```

### control

L'attribut "controls" peut prendre la valeur true (vrai) ou false (faux) et permet de gérer l'apparition de commandes telles que le bouton de lecture/pause ou le curseur de volume. Vous lui attribuez la valeur true en l'ajoutant à la balise. S'il n'est pas présent dans la balise, il prend la valeur false.


```html
<video controls>
  <source src="video.mp4" type="video/mp4" />
</video>
```

Il existe de nombreux autres attributs facultatifs qui peuvent être ajoutés pour personnaliser le lecteur vidéo dans la page. Pour en savoir plus, cliquez sur les liens ci-dessous.

## Exemple de stockage Web HTML5

Le stockage Web permet aux applications Web de stocker jusqu'à 5 Mo d'informations dans le stockage du navigateur par origine (par domaine et par protocole).

### Types de stockage Web

Il existe deux objets pour le stockage des données sur le client :

`window.localStorage` : stocke les données sans date d'expiration et vit jusqu'à ce qu'il soit supprimé.


```js
// Store Item
localStorage.setItem("foo", "bar");

// Get Item
localStorage.getItem("foo"); //returns "bar"
```

`window.sessionStorage` : stocke les données pour une session, où les données sont perdues lorsque le navigateur / l'onglet du navigateur est fermé.

```js
// Store Item
sessionStorage.setItem("foo", "bar");

// Get Item
sessionStorage.getItem("foo"); //returns "bar"
```

Étant donné que l'implémentation actuelle ne prend en charge que les mappings de chaîne à chaîne, vous devez sérialiser et dé-sérialiser d'autres structures de données.

Vous pouvez le faire en utilisant JSON.stringify() et JSON.parse().

Par exemple, pour le fichier JSON donné


```
var jsonObject = { 'one': 1, 'two': 2, 'three': 3 };
```

Nous convertissons d'abord l'objet JSON en chaîne et le sauvegardons dans le stockage local :

```
localStorage.setItem('jsonObjectString', JSON.stringify(jsonObject));
```
Pour obtenir l'objet JSON à partir de la chaîne stockée dans le stockage local :

```
var jsonObject = JSON.parse(localStorage.getItem('jsonObjectString'));
```

## Exemple de liens Mailto
Un lien mailto est une sorte de lien hypertexte (`<a href=""></a>`) avec des paramètres spéciaux qui vous permettent de spécifier des destinataires supplémentaires, une ligne d'objet et/ou un corps de texte.

### La syntaxe de base avec un destinataire est :

```
<a href="mailto:friend@something.com">Some text</a>
```

### Plus de personnalisation !

### Ajout d'un objet à ce courrier :

Si vous souhaitez ajouter un objet spécifique à ce courrier, veillez à ajouter %20 ou + partout où il y a un espace dans la ligne d'objet. Un moyen facile de s'assurer qu'il est correctement formaté est d'utiliser un [décodeur/encodeur d'URL](https://meyerweb.com/eric/tools/dencoder/).

### Ajout du corps du texte :

De la même manière, vous pouvez ajouter un message spécifique dans la partie corps de l'e-mail : Là encore, les espaces doivent être remplacés par `%20` ou `+`. Après le paramètre objet, tout paramètre supplémentaire doit être précédé de `&`.

Exemple : Disons que vous voulez que les utilisateurs envoient un e-mail à leurs amis sur leurs progrès au Free Code Camp :

Adresse : vide

Sujet : Grande nouvelle

Corps : Je deviens un développeur

Votre lien html maintenant :


```html
<a href="mailto:?subject=Great%20news&body=I%20am%20becoming%20a%20developer">Send mail!</a>
```

Ici, nous avons laissé le mailto vide (`mailto: ?`). Cela ouvrira le client de messagerie de l'utilisateur et ce dernier ajoutera lui-même l'adresse du destinataire.

### Ajouter d'autres destinataires :

De la même manière, vous pouvez ajouter des paramètres CC et bcc. Séparez chaque adresse par une virgule !

Les paramètres supplémentaires doivent être précédés de `&`.

```html
<a href="mailto:firstfriend@something.com?subject=Great%20news&cc=secondfriend@something.com,thirdfriend@something.com&bcc=fourthfriend@something.com">Send mail!</a>
```

## Merci d'avoir utilisé cette référence HTML. Bon codage !

