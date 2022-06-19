https://www.freecodecamp.org/news/fetch-data-react/

# Comment récupérer des données dans React : Aide-mémoire + exemples

Il existe de nombreuses façons de récupérer des données à partir d'une API externe dans React. Mais laquelle devriez-vous utiliser pour vos applications en 2021 ?

Dans ce tutoriel, nous allons passer en revue cinq des modèles les plus couramment utilisés pour récupérer des données avec React en effectuant une requête HTTP vers une API REST.

Nous ne couvrirons pas seulement comment récupérer des données, mais aussi comment gérer au mieux le chargement et l'état d'erreur lors de la récupération de nos données.

C'est parti !

    Pour tous ces exemples, nous utiliserons un point de terminaison de la populaire API JSON Placeholder, mais vous pouvez utiliser votre propre API que vous avez créée (comme une API Node avec Express) ou toute autre API publique.

## Vous voulez votre propre copie ?

Cliquez ici pour télécharger la fiche technique au format PDF (cela prend 5 secondes).

Elle comprend toutes les informations essentielles sous la forme d'un guide PDF pratique.

### 1. Comment récupérer des données dans React à l'aide de l'API Fetch ?

La façon la plus accessible de récupérer des données avec React est d'utiliser l'API Fetch.

L'API Fetch est un outil intégré à la plupart des navigateurs modernes dans l'objet window (`window.fetch`) et nous permet de faire des requêtes HTTP très facilement en utilisant des promesses JavaScript.

Pour effectuer une simple requête GET avec fetch, il suffit d'inclure le point de terminaison de l'URL vers lequel nous voulons effectuer notre requête. Nous voulons effectuer cette requête une fois que notre composant React est monté.

Pour ce faire, nous effectuons notre requête dans le crochet useEffect et nous nous assurons de fournir un tableau de dépendances vide comme deuxième argument, afin que notre requête ne soit effectuée qu'une seule fois (en supposant qu'elle ne dépende d'aucune autre donnée de notre composant).


Dans le premier callback `.then()`, nous vérifions si la réponse est correcte (`response.ok`). Si c'est le cas, nous renvoyons notre réponse pour la transmettre à la callback suivante, puis la rappeler sous forme de données JSON, puisque ce sont les données que nous recevrons de notre API d'utilisateur aléatoire.

Si la réponse n'est pas correcte, nous supposons qu'une erreur s'est produite lors de la requête. En utilisant fetch, nous devons gérer les erreurs nous-mêmes, donc nous lançons la `réponse` comme une `erreur` pour qu'elle soit traitée par notre `callback` catch.

Ici, dans notre exemple, nous mettons nos données d'erreur dans l'état avec `setError`. S'il y a une erreur, nous retournons le texte "Error !

    Notez que vous pouvez également afficher un message d'erreur à partir de l'objet d'erreur que nous avons placé dans l'état en utilisant `error.message`.

Nous utilisons le callback `.finally()` comme fonction qui est appelée lorsque notre promesse a été résolue avec succès ou non. Dans cette fonction, nous définissons loading à false, de sorte que nous ne voyons plus notre texte de chargement.

Au lieu de cela, nous voyons soit nos données sur la page si la requête a été effectuée avec succès, soit qu'il y a eu une erreur lors de la requête dans le cas contraire.

### 2. Comment récupérer des données dans React en utilisant Axios

La deuxième approche pour effectuer des requêtes avec React consiste à utiliser la bibliothèque `axios`.

Dans cet exemple, nous allons simplement réviser notre exemple Fetch en installant d'abord `axios` à l'aide de npm :


```js
npm install axios
```

Ce qu'axios nous permet de faire est d'utiliser exactement la même syntaxe de promesse que fetch - mais au lieu d'utiliser notre premier callback then pour déterminer manuellement si la réponse est correcte et lancer une erreur, axios s'en occupe pour nous.

De plus, il nous permet, dans ce premier callback, de récupérer les données JSON de `response.data`.

Ce qui est pratique dans l'utilisation d'axios, c'est qu'il a une syntaxe beaucoup plus courte qui nous permet de réduire notre code et qu'il inclut de nombreux outils et fonctionnalités que Fetch n'a pas dans son API.

Toutes ces raisons expliquent pourquoi elle est devenue la bibliothèque HTTP de référence pour les développeurs React.


### 3. Comment récupérer des données dans React à l'aide de la syntaxe async / await

Dans ES7, il est devenu possible de résoudre des promesses en utilisant la syntaxe `async / await`.

L'avantage est qu'elle nous permet de supprimer nos callbacks `.then()`, `.catch()` et .`finally()` et de récupérer simplement nos données résolues de manière asynchrone comme si nous écrivions du code synchrone sans promesses.

En d'autres termes, nous ne devons pas compter sur les callbacks lorsque nous utilisons `async / await` avec React.

Nous devons être conscients du fait que lorsque nous utilisons `useEffect`, la fonction effect (le premier argument) ne peut pas devenir une fonction `async`.

Si nous jetons un coup d'oeil à l'erreur de linting que React nous donne si nous avons utilisé Create React App pour construire notre projet, il nous sera dit que cette fonction ne peut pas être asynchrone pour éviter les conditions de course. 


Par conséquent, au lieu de rendre cette fonction asynchrone, nous pouvons simplement créer une fonction asynchrone distincte dans notre composant, que nous pouvons appeler de manière synchrone. C'est-à-dire, sans le mot-clé `await` devant.

Dans cet exemple, nous créons une fonction asynchrone appelée `getData`. En l'appelant de manière synchrone dans `useEffect`, nous pouvons récupérer nos données comme prévu.

### 4. Comment récupérer des données dans React en utilisant un crochet React personnalisé (useFetch)

Au fil du temps, vous vous rendrez peut-être compte qu'il devient un peu fastidieux et chronophage de continuer à écrire le hook `useEffect` avec tout son boilerplate dans chaque composant dans lequel vous voulez récupérer des données.

Pour réduire le code réutilisé, nous pouvons utiliser un hook personnalisé comme une abstraction spéciale, que nous pouvons écrire nous-mêmes à partir d'une bibliothèque tierce (comme nous le faisons ici, en utilisant la bibliothèque `react-fetch-hook`).

Un hook personnalisé qui effectue notre requête HTTP nous permet de rendre nos composants beaucoup plus concis. Tout ce que nous avons à faire est d'appeler notre hook au sommet de notre composant.


Dans ce cas, nous récupérons toutes les données, le chargement et l'état d'erreur dont nous avons besoin pour pouvoir utiliser la même structure pour notre composant qu'auparavant, mais sans avoir à `useEffect`. De plus, nous n'avons plus besoin d'écrire impérativement comment résoudre notre promesse à partir de notre requête GET à chaque fois que nous voulons faire une requête.

### 5. Comment récupérer des données dans React en utilisant la bibliothèque React Query ?

L'utilisation de hooks personnalisés est une excellente approche pour écrire des requêtes HTTP beaucoup plus concises afin d'obtenir nos données et tout leur état associé. Mais React Query est une bibliothèque qui permet de passer à la vitesse supérieure en matière de récupération de données à l'aide de hooks.

React Query nous permet non seulement d'utiliser des hooks personnalisés que nous pouvons réutiliser à travers nos composants de manière concise, mais elle nous offre également un grand nombre d'outils de gestion d'état pour pouvoir contrôler quand, comment et à quelle fréquence nos données sont récupérées.

En particulier, React Query nous donne un cache, que vous pouvez voir ci-dessous grâce aux Devtools de React Query. Cela nous permet de gérer facilement les requêtes que nous avons effectuées en fonction de la valeur clé que nous spécifions pour chaque requête.

Pour les requêtes ci-dessous, notre requête pour nos données d'utilisateurs aléatoires est identifiée par la chaîne 'random-user' (fournie comme premier argument de `useQuery`).

En faisant référence à cette clé, nous pouvons faire des choses puissantes comme récupérer, valider ou réinitialiser nos différentes requêtes.

    Si nous nous fions à notre solution de crochet personnalisé ou à useEffect, nous allons récupérer nos données à chaque fois que notre composant est monté. Dans la plupart des cas, cela est inutile. Si notre état externe n'a pas changé, nous ne devrions idéalement pas avoir à montrer l'état de chargement à chaque fois que nous affichons notre composant.

React Query améliore grandement notre expérience utilisateur en essayant de servir nos données à partir de son cache d'abord, puis de mettre à jour les données en arrière-plan pour afficher les changements si l'état de notre API a changé.

## Il nous donne également un arsenal d'outils puissants pour mieux gérer nos requêtes en fonction de l'évolution de nos données à travers notre requête.

Par exemple, si notre application nous permettait d'ajouter un utilisateur différent, nous pourrions vouloir récupérer à nouveau cette requête, une fois l'utilisateur ajouté. Si nous savons que la requête est modifiée très fréquemment, nous pourrions spécifier qu'elle doit être rafraîchie toutes les minutes environ. Ou qu'elle soit rafraîchie chaque fois que l'utilisateur concentre l'onglet de sa fenêtre.

En bref, React Query est la solution idéale non seulement pour effectuer des requêtes de manière concise, mais aussi pour gérer de manière efficace et efficiente les données qui sont renvoyées pour nos requêtes HTTP à travers les composants de notre application.
Vous souhaitez conserver ce guide pour vous y référer ultérieurement ?
