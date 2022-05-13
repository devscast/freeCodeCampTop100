https://www.freecodecamp.org/news/json-stringify-example-how-to-parse-a-json-object-with-javascript/

## Exemple de JSON Stringify - Comment analyser un objet JSON avec JS

**JSON, ou JavaScript Object Notation, est omniprésent. Si vous avez déjà utilisé une application Web, il y a de fortes chances qu'elle ait utilisé JSON pour structurer, stocker et transmettre des données entre ses serveurs et votre appareil.**

Dans cet article, nous passerons brièvement en revue les différences entre JSON et JavaScript, puis nous aborderons les différentes façons d'analyser JSON avec JavaScript dans le navigateur et dans les projets Node.js.

## Différences entre JSON et JavaScript

Bien que JSON ressemble à du JavaScript ordinaire, il est préférable de considérer JSON comme un format de données, similaire à un fichier texte. Il se trouve que JSON s'inspire de la syntaxe JavaScript, ce qui explique leur ressemblance.

Jetons un coup d'œil aux objets JSON et aux tableaux JSON et comparons-les à leurs homologues JavaScript.

### Objets JSON et littéraux d'objets JavaScript

Tout d'abord, voici un objet JSON :

```json
{
  "name": "Jane Doe",
  "favorite-game": "Stardew Valley",
  "subscriber": false
}
```

La principale différence entre un objet JSON et un objet JavaScript ordinaire (également appelé objet littéral) réside dans les guillemets. Toutes les clés et les valeurs de type chaîne de caractères d'un objet JSON doivent être entourées de guillemets doubles (`"`).

Les littéraux d'objet JavaScript sont un peu plus souples. Avec les littéraux d'objet, il n'est pas nécessaire d'entourer les clés et les chaînes de caractères de guillemets doubles. Vous pouvez utiliser des guillemets simples (`'`) ou n'utiliser aucun type de guillemet pour les clés.

Voici à quoi pourrait ressembler le code ci-dessus en tant que littéral d'objet JavaScript :


```js
const profile = {
  name: 'Jane Doe',
  'favorite-game': 'Stardew Valley',
  subscriber: false
}
```

Notez que la clé `"favorite-game"` est placée entre guillemets simples. Avec les littéraux d'objet, vous devrez mettre entre guillemets les clés dont les mots sont séparés par des tirets (`-`).

Si vous souhaitez éviter les guillemets, vous pouvez réécrire la clé pour utiliser la casse (`favoriteGame`) ou séparer les mots par un trait de soulignement (`favorite_game`).

### Tableaux JSON et tableaux JavaScript

Les tableaux JSON fonctionnent à peu près de la même manière que les tableaux en JavaScript et peuvent contenir des chaînes, des booléens, des nombres et d'autres objets JSON. Par exemple :

```json 
[
  {
    "name": "Jane Doe",
    "favorite-game": "Stardew Valley",
    "subscriber": false
  },
  {
    "name": "John Doe",
    "favorite-game": "Dragon Quest XI",
    "subscriber": true
  }
]
```

Voici à quoi cela pourrait ressembler en JavaScript :


```js
const profiles = [
  {
    name: 'Jane Doe',
    'favorite-game': 'Stardew Valley',
    subscriber: false
  },
  {
    name: 'John Doe',
    'favorite-game': 'Dragon Quest XI',
    subscriber: true
  }
];
```

## JSON sous forme de chaîne

Vous vous demandez peut-être si vous ne pouvez pas utiliser les objets et tableaux JSON dans votre programme comme un objet littéral ou un tableau JavaScript ordinaire.

La raison pour laquelle vous ne pouvez pas le faire est que JSON n'est en fait qu'une chaîne de caractères.

Par exemple, lorsque vous écrivez JSON dans un fichier séparé comme dans `jane-profile.json` ou `profiles.json` ci-dessus, ce fichier contient en fait du texte sous la forme d'un objet ou d'un tableau JSON, qui ressemble à du JavaScript.

Et si vous faites une demande à une API, elle renverra quelque chose comme ceci :

```json
{"name":"Jane Doe","favorite-game":"Stardew Valley","subscriber":false}
```

Comme pour les fichiers texte, si vous souhaitez utiliser JSON dans votre projet, vous devrez l'analyser ou le transformer en quelque chose que votre langage de programmation peut comprendre. Par exemple, l'analyse d'un objet JSON en Python créera un dictionnaire.

Après avoir compris cela, examinons les différentes façons d'analyser JSON en JavaScript.

## Comment analyser JSON dans le navigateur ?

Si vous travaillez avec JSON dans le navigateur, vous êtes probablement en train de recevoir ou d'envoyer des données via une API.

Jetons un coup d'œil à quelques exemples.

### Comment analyser JSON avec `fetch` ?

La façon la plus simple d'obtenir des données à partir d'une API est d'utiliser `fetch`, qui inclut la méthode `.json()` pour analyser automatiquement les réponses JSON en un objet littéral ou un tableau JavaScript utilisable.

Voici un code qui utilise `fetch` pour effectuer une requête `GET` pour une blague sur le thème du développement à partir de l'API gratuite [Chuck Norris Jokes](https://api.chucknorris.io/) :


```js
fetch('https://api.chucknorris.io/jokes/random?category=dev')
  .then(res => res.json()) // the .json() method parses the JSON response into a JS object literal
  .then(data => console.log(data));
```

Si vous exécutez ce code dans le navigateur, vous verrez quelque chose comme ceci dans la console :

```json
{
    "categories": ["dev"],
    "created_at": "2020-01-05 13:42:19.324003",
    "icon_url": "https://assets.chucknorris.host/img/avatar/chuck-norris.png",
    "id": "elgv2wkvt8ioag6xywykbq",
    "updated_at": "2020-01-05 13:42:19.324003",
    "url": "https://api.chucknorris.io/jokes/elgv2wkvt8ioag6xywykbq",
    "value": "Chuck Norris's keyboard doesn't have a Ctrl key because nothing controls Chuck Norris."
}
```

Bien que cela ressemble à un objet JSON, il s'agit en réalité d'un objet JavaScript littéral, et vous pouvez l'utiliser librement dans votre programme.

### Comment stringifier JSON avec `JSON.stringify()`

Mais que se passe-t-il si vous voulez envoyer des données à une API ?

Par exemple, supposons que vous souhaitiez envoyer une blague de Chuck Norris à l'API des blagues de Chuck Norris afin que d'autres personnes puissent la lire plus tard.

Tout d'abord, vous écrivez votre blague sous la forme d'un objet JS littéral :

```js
const newJoke = {
  categories: ['dev'],
  value: "Chuck Norris's keyboard is made up entirely of Cmd keys because Chuck Norris is always in command."
};
```

Puis, comme vous envoyez des données à une API, vous devez transformer votre objet littéral `newJoke` en une chaîne JSON.

Heureusement, JavaScript comprend une méthode très utile pour ce faire : `JSON.stringify()` :

```js
const newJoke = {
  categories: ['dev'],
  value: "Chuck Norris's keyboard is made up entirely of Cmd keys because Chuck Norris is always in command."
};

console.log(JSON.stringify(newJoke)); // {"categories":["dev"],"value":"Chuck Norris's keyboard is made up entirely of Cmd keys because Chuck Norris is always in command."}

console.log(typeof JSON.stringify(newJoke)); // string
```

Bien que nous convertissions un objet littéral en une chaîne JSON dans cet exemple, `JSON.stringify()` fonctionne également avec les tableaux.

Enfin, il ne vous reste plus qu'à renvoyer votre blague JSON stringifiée à l'API par une requête `POST`.

Notez que l'API Chuck Norris Jokes ne dispose pas de cette fonctionnalité. Mais si c'était le cas, voici à quoi pourrait ressembler le code :

```js
const newJoke = {
  categories: ['dev'],
  value: "Chuck Norris's keyboard is made up entirely of Cmd keys because Chuck Norris is always in command."
};

fetch('https://api.chucknorris.io/jokes/submit', { // fake API endpoint
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify(newJoke), // turn the JS object literal into a JSON string
})
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => {
    console.error(err);
  });
```

Et comme ça, vous avez analysé le JSON entrant avec `fetch` et utilisé `JSON.stringify()` pour convertir un objet JS littéral en une chaîne JSON.

### Comment travailler avec des fichiers JSON locaux dans le navigateur ?

Malheureusement, il n'est pas possible (ou conseillé) de charger un fichier JSON local dans le navigateur.

`fetch` lancera une erreur si vous essayez de charger un fichier local. Par exemple, disons que vous avez un fichier JSON avec quelques blagues :

```json
[
  {
    "categories": ["dev"],
    "created_at": "2020-01-05 13:42:19.324003",
    "icon_url": "https://assets.chucknorris.host/img/avatar/chuck-norris.png",
    "id": "elgv2wkvt8ioag6xywykbq",
    "updated_at": "2020-01-05 13:42:19.324003",
    "url": "https://api.chucknorris.io/jokes/elgv2wkvt8ioag6xywykbq",
    "value": "Chuck Norris's keyboard doesn't have a Ctrl key because nothing controls Chuck Norris."
  },
  {
    "categories": ["dev"],
    "created_at": "2020-01-05 13:42:19.324003",
    "icon_url": "https://assets.chucknorris.host/img/avatar/chuck-norris.png",
    "id": "ae-78cogr-cb6x9hluwqtw",
    "updated_at": "2020-01-05 13:42:19.324003",
    "url": "https://api.chucknorris.io/jokes/ae-78cogr-cb6x9hluwqtw",
    "value": "There is no Esc key on Chuck Norris' keyboard, because no one escapes Chuck Norris."
  }
]
```

Et vous voulez l'analyser et créer une liste de blagues sur une simple page HTML.

Si vous créez une page avec le texte suivant et l'ouvrez dans votre navigateur :


```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
    <meta name="viewport" content="width=device-width" />
    <title>Fetch Local JSON</title>
  </head>
  <script>
    fetch("./jokes.json", { mode: "no-cors" }) // disable CORS because path does not contain http(s)
      .then((res) => res.json())
      .then((data) => console.log(data));
  </script>
</html>
```

Vous verrez ceci dans la console :

```
Fetch API cannot load file://<path>/jokes.json. URL scheme "file" is not supported
```

Par défaut, les navigateurs n'autorisent pas l'accès aux fichiers locaux pour des raisons de sécurité. C'est une bonne chose, et vous ne devriez pas essayer de contourner ce comportement.

La meilleure chose à faire est de convertir le fichier JSON local en JavaScript. Heureusement, c'est assez facile puisque la syntaxe JSON est très similaire à celle de JavaScript.

Il vous suffit de créer un nouveau fichier et de déclarer votre JSON en tant que variable :

```js
const jokes = [
  {
    "categories": ["dev"],
    "created_at": "2020-01-05 13:42:19.324003",
    "icon_url": "https://assets.chucknorris.host/img/avatar/chuck-norris.png",
    "id": "elgv2wkvt8ioag6xywykbq",
    "updated_at": "2020-01-05 13:42:19.324003",
    "url": "https://api.chucknorris.io/jokes/elgv2wkvt8ioag6xywykbq",
    "value": "Chuck Norris's keyboard doesn't have a Ctrl key because nothing controls Chuck Norris."
  },
  {
    "categories": ["dev"],
    "created_at": "2020-01-05 13:42:19.324003",
    "icon_url": "https://assets.chucknorris.host/img/avatar/chuck-norris.png",
    "id": "ae-78cogr-cb6x9hluwqtw",
    "updated_at": "2020-01-05 13:42:19.324003",
    "url": "https://api.chucknorris.io/jokes/ae-78cogr-cb6x9hluwqtw",
    "value": "There is no Esc key on Chuck Norris' keyboard, because no one escapes Chuck Norris."
  }
]
```

Et ajoutez-le à votre page comme un script séparé :

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
    <meta name="viewport" content="width=device-width" />
    <title>Fetch Local JSON</title>
  </head>
  <script src="jokes.js"></script>
  <script>
    console.log(jokes);
  </script>
</html>
```

Vous pouvez également utiliser des [modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules) JavaScript pour faire la même chose, mais cela sort un peu du cadre de cet article.

Mais que faire si vous voulez travailler avec des fichiers JSON locaux et que Node.js est installé ? Voyons maintenant comment faire.

### Comment analyser JSON dans Node.js ?

Node.js est un moteur d'exécution JavaScript qui vous permet d'exécuter JavaScript en dehors du navigateur. Vous pouvez lire tout sur [Node.js ici](https://www.freecodecamp.org/news/the-definitive-node-js-handbook-6912378afc6e/).

Que vous utilisiez Node.js pour exécuter du code localement sur votre ordinateur, ou pour exécuter des applications web entières sur un serveur, il est bon de savoir comment travailler avec JSON.

Pour les exemples suivants, nous utiliserons le même fichier `jokes.json` :

```json
[
  {
    "categories": ["dev"],
    "created_at": "2020-01-05 13:42:19.324003",
    "icon_url": "https://assets.chucknorris.host/img/avatar/chuck-norris.png",
    "id": "elgv2wkvt8ioag6xywykbq",
    "updated_at": "2020-01-05 13:42:19.324003",
    "url": "https://api.chucknorris.io/jokes/elgv2wkvt8ioag6xywykbq",
    "value": "Chuck Norris's keyboard doesn't have a Ctrl key because nothing controls Chuck Norris."
  },
  {
    "categories": ["dev"],
    "created_at": "2020-01-05 13:42:19.324003",
    "icon_url": "https://assets.chucknorris.host/img/avatar/chuck-norris.png",
    "id": "ae-78cogr-cb6x9hluwqtw",
    "updated_at": "2020-01-05 13:42:19.324003",
    "url": "https://api.chucknorris.io/jokes/ae-78cogr-cb6x9hluwqtw",
    "value": "There is no Esc key on Chuck Norris' keyboard, because no one escapes Chuck Norris."
  }
]
```

### Comment analyser un fichier JSON avec `require()`

Commençons par la méthode la plus simple.

Si vous avez un fichier JSON local, tout ce que vous avez à faire est d'utiliser `require()` pour le charger comme tout autre module Node.js :

```js
const jokes = require('./jokes.json');
```

Le fichier JSON sera automatiquement analysé pour vous et vous pourrez commencer à l'utiliser dans votre projet :

```js
const jokes = require('./jokes.json');

console.log(jokes[0].value); // "Chuck Norris's keyboard doesn't have a Ctrl key because nothing controls Chuck Norris."
```

Notez que cette opération est synchrone, ce qui signifie que votre programme s'arrêtera jusqu'à ce qu'il ait analysé l'ensemble du fichier avant de continuer. Les fichiers `JSON` très volumineux peuvent ralentir votre programme, alors faites attention.

De plus, comme l'analyse du `JSON` de cette manière charge l'ensemble du fichier en mémoire, il est préférable d'utiliser cette méthode pour les fichiers `JSON` statiques. Si le fichier `JSON` est modifié pendant l'exécution de votre programme, vous n'aurez pas accès à ces modifications tant que vous n'aurez pas redémarré votre programme et analysé le fichier `JSON` mis à jour.

### Comment analyser un fichier JSON avec `fs.readFileSync()` et `JSON.parse()` ?

C'est la façon la plus traditionnelle (faute d'un meilleur terme) d'analyser les fichiers JSON dans les projets Node.js - lire le fichier avec le module `fs` (système de fichiers), puis l'analyser avec `JSON.parse()`.

Voyons comment faire cela avec la méthode `fs.readFileSync()`. Tout d'abord, ajoutez le module `fs` à votre projet :

```js
const fs = require('fs');
```

Ensuite, créez une nouvelle variable pour stocker la sortie du fichier `jokes.json` et définissez-la comme étant égale à `fs.readFileSync()` :

```js
const fs = require('fs');
const jokesFile = fs.readFileSync();
```

`fs.readFileSync()` prend quelques arguments. Le premier est le chemin d'accès au fichier que vous voulez lire :

```js
const fs = require('fs');
const jokesFile = fs.readFileSync('./jokes.json');
```

Mais si vous enregistrez `jokesFile` sur la console maintenant, vous verrez quelque chose comme ça :

```
<Buffer 5b 0a 20 20 7b 0a 20 20 20 20 22 63 61 74 65 67 6f 72 69 65 73 22 3a 20 5b 22 64 65 76 22 5d 2c 0a 20 20 20 20 22 63 72 65 61 74 65 64 5f 61 74 22 3a ... 788 more bytes>
```

Cela signifie simplement que le module `fs` est en train de lire le fichier, mais qu'il ne connaît pas l'encodage ou le format du fichier. `fs` peut être utilisé pour charger à peu près n'importe quel fichier, et pas seulement les fichiers texte comme JSON, donc nous devons lui indiquer comment le fichier est encodé.

Pour les fichiers texte, l'encodage est généralement `utf8` :


```js
const fs = require('fs');
const jokesFile = fs.readFileSync('./jokes.json', 'utf8');
```

Maintenant, si vous enregistrez `jokesFile` dans la console, vous verrez le contenu du fichier.

Mais pour l'instant, nous ne faisons que lire le fichier, et il s'agit toujours d'une chaîne. Nous devons utiliser une autre méthode pour analyser `jokesFile` et le transformer en un objet ou un tableau JavaScript utilisable.

Pour ce faire, nous allons utiliser `JSON.parse()` :

```js
const fs = require('fs');
const jokesFile = fs.readFileSync('./jokes.json', 'utf8');
const jokes = JSON.parse(jokesFile);

console.log(jokes[0].value); // "Chuck Norris's keyboard doesn't have a Ctrl key because nothing controls Chuck Norris."
```

Comme son nom l'indique, `JSON.parse()` prend une chaîne JSON et l'analyse en un objet JavaScript littéral ou un tableau.

Comme pour la méthode `require` ci-dessus, `fs.readFileSync()` est une méthode synchrone, ce qui signifie qu'elle peut ralentir votre programme s'il lit un fichier volumineux, JSON ou autre.

En outre, elle ne lit le fichier qu'une seule fois et le charge en mémoire. Si le fichier est modifié, vous devrez le relire à un moment donné. Pour faciliter les choses, vous pouvez créer une fonction simple pour lire les fichiers.

Voici à quoi cela pourrait ressembler :

```js
const fs = require('fs');
const readFile = path => fs.readFileSync(path, 'utf8');

const jokesFile1 = readFile('./jokes.json');
const jokes1 = JSON.parse(jokesFile1);

console.log(jokes1[0].value); // "Chuck Norris's keyboard doesn't have a Ctrl key because nothing controls Chuck Norris."

// the jokes.json file changes at some point

const jokesFile2 = readFile('./jokes.json');
const jokes2 = JSON.parse(jokesFile2);

console.log(jokes2[0].value); // "Chuck Norris's keyboard is made up entirely of Cmd keys because Chuck Norris is always in command."
```

### Comment analyser JSON avec `fs.readFile()` et `JSON.parse()`

La méthode `fs.readFile()` est très similaire à `fs.readFileSync()`, sauf qu'elle fonctionne de manière asynchrone. C'est idéal si vous avez un gros fichier à lire et que vous ne voulez pas que cela retarde le reste de votre code.

Voici un exemple de base :

```js
const fs = require('fs');

fs.readFile('./jokes.json', 'utf8');
```

Jusqu'à présent, cela ressemble à ce que nous avons fait avec `fs.readFileSync()`, sauf que nous ne l'assignons pas à une variable comme `jokesFile`. Parce que c'est asynchrone, tout code après `fs.readFile()` sera exécuté avant que la lecture du fichier ne soit terminée.

Au lieu de cela, nous allons utiliser une fonction de rappel et analyser le JSON à l'intérieur de celle-ci :

```js
const fs = require('fs');

fs.readFile('./jokes.json', 'utf8', (err, data) => {
  if (err) console.error(err);
  const jokes = JSON.parse(data);

  console.log(jokes[0].value);
});

console.log("This will run first!");
```

Qui imprime ce qui suit à la console :

```
This will run first!
Chuck Norris's keyboard doesn't have a Ctrl key because nothing controls Chuck Norris.
```

Comme avec `fs.readFileSync()`, `fs.readFile()` charge le fichier en mémoire, ce qui signifie que vous devrez relire le fichier s'il est modifié.

De plus, même si `fs.readFile()` est asynchrone, il finit par charger tout le fichier qu'il lit en mémoire. Si vous avez un fichier volumineux, il est préférable d'utiliser les [flux Node.js](https://www.freecodecamp.org/news/node-js-streams-everything-you-need-to-know-c9141306be93/).

### Comment stringifier JSON avec J`SON.stringify()` en Node.js ?

Enfin, si vous analysez JSON avec Node.js, il y a de fortes chances que vous deviez retourner JSON à un moment donné, peut-être en tant que réponse API.

Heureusement, cela fonctionne de la même manière que dans le navigateur - il suffit d'utiliser `JSON.stringify()` pour convertir les littéraux d'objets JavaScript ou les tableaux en une chaîne JSON :


```js
const newJoke = {
  categories: ['dev'],
  value: "Chuck Norris's keyboard is made up entirely of Cmd keys because Chuck Norris is always in command."
};

console.log(JSON.stringify(newJoke)); // {"categories":["dev"],"value":"Chuck Norris's keyboard is made up entirely of Cmd keys because Chuck Norris is always in command."}
```

Et c'est tout ! Nous avons couvert à peu près tout ce que vous devez savoir sur le travail avec JSON dans le navigateur et dans les projets Node.js.

Maintenant, allez-y et parsez ou stringifiez JSON à votre guise.

Ai-je manqué quelque chose ? Comment analysez-vous JSON dans vos projets ? Faites-le moi savoir sur Twitter.




