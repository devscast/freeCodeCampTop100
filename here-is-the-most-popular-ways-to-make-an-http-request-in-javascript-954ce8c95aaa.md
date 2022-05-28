![img cover](https://cdn-media-1.freecodecamp.org/images/1*gqHgCNubMncv7EwWNdArGQ.png)

JavaScript dispose d'excellents modules et méthodes pour effectuer des requêtes HTTP qui peuvent être utilisées pour envoyer ou recevoir des données d'une ressource côté serveur. Dans cet article, nous allons examiner quelques méthodes populaires pour effectuer des requêtes HTTP en JavaScript.

## Ajax

Ajax est la manière traditionnelle d'effectuer une requête HTTP asynchrone. Les données peuvent être envoyées en utilisant la méthode HTTP POST et reçues en utilisant la méthode HTTP GET. Jetons un coup d'oeil et faisons une requête ==GET==. Je vais utiliser JSONPlaceholder, une API REST en ligne gratuite pour les développeurs qui renvoie des données aléatoires au format JSON.

Pour effectuer un appel HTTP en Ajax, vous devez initialiser une nouvelle méthode ==XMLHttpRequest()==, spécifier le point de terminaison de l'URL et la méthode HTTP (dans ce cas, GET). Enfin, nous utilisons la méthode ==open()== pour lier la méthode HTTP et le point de terminaison de l'URL et appelons la méthode ==send()== pour lancer la requête.

Nous enregistrons la réponse HTTP dans la console en utilisant la propriété ==XMLHTTPRequest.onreadystatechange== qui contient le gestionnaire d'événement à appeler lorsque l'événement readystatechanged est déclenché.

![img code](https://cdn-media-1.freecodecamp.org/images/1*zXtlRe4yRF3tZkFFvBhZeA.png)

```js
const Http = new XMLHttpRequest();
const url='https://jsonplaceholder.typicode.com/posts';
Http.open("GET", url);
Http.send();

Http.onreadystatechange = (e) => {
  console.log(Http.responseText)
}
```

Si vous consultez la console de votre navigateur, elle renverra un tableau de données au format JSON. Mais comment savoir si la requête est terminée ? En d'autres termes, comment pouvons-nous traiter les réponses avec Ajax ?

La propriété ==onreadystatechange== possède deux méthodes, ==readyState== et ==status==, qui nous permettent de vérifier l'état de notre requête.

![img code](https://cdn-media-1.freecodecamp.org/images/1*UfZf6qaZwNh5Mptft4WIZA.png)

Si ==readyState== est égal à 4, cela signifie que la requête est terminée. La propriété ==readyState== a 5 réponses. Pour en savoir plus, [cliquez ici](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState).

En dehors de la réalisation directe d'un appel Ajax avec JavaScript, il existe d'autres méthodes plus puissantes pour réaliser un appel HTTP, comme ==$.Ajax== qui est une méthode jQuery. Je vais en parler maintenant.

## Méthodes jQuery

jQuery dispose de nombreuses méthodes pour gérer facilement les requêtes HTTP. Afin d'utiliser ces méthodes, vous devez inclure la bibliothèque jQuery dans votre projet.

```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
```

## $.ajax

jQuery Ajax est l'une des méthodes les plus simples pour effectuer un appel HTTP.

![img code](https://cdn-media-1.freecodecamp.org/images/1*vZ4BqVQfsvtpJm_RCsCE2Q.png)

La méthode $.ajax prend de nombreux paramètres, dont certains sont obligatoires et d'autres facultatifs. Elle contient deux options de rappel ==success== et ==error== pour gérer la réponse reçue.
## Méthode $.get

La méthode $.get est utilisée pour exécuter des requêtes GET. Elle prend deux paramètres : le point de terminaison et une fonction de rappel.

![img code](https://cdn-media-1.freecodecamp.org/images/1*2koN5FJuT68WIyRKTihe5w.png)

## $.post

La méthode ==$.post== est un autre moyen d'envoyer des données au serveur. Elle prend trois paramètres : l'==url==, les données que vous voulez envoyer, et une fonction de rappel.

![img code](https://cdn-media-1.freecodecamp.org/images/1*ql6Yp1EJfD7850GXhErwyw.png)

## $.getJSON

La méthode $.getJSON récupère uniquement les données au format JSON. Elle prend deux paramètres : l'url et une fonction de rappel.

![img code](https://cdn-media-1.freecodecamp.org/images/1*hdcFdVHiBiRAo1YOi_Kt0Q.png)

jQuery dispose de toutes ces méthodes pour demander ou envoyer des données à un serveur distant. Mais vous pouvez en fait regrouper toutes ces méthodes en une seule : la méthode ==$.ajax==, comme le montre l'exemple ci-dessous :

![img code](https://cdn-media-1.freecodecamp.org/images/1*soPARjfQXMcZ5ccPK1QMmA.png)


## fetch

==fetch== est une nouvelle API Web puissante qui vous permet d'effectuer des requêtes asynchrones. En fait, ==fetch== est l'un des meilleurs moyens, et mon préféré, de faire une requête HTTP. Elle renvoie une "promesse", ce qui est l'une des grandes caractéristiques de ES6. Si vous n'êtes pas familier avec ES6, vous pouvez lire [cet article](https://medium.freecodecamp.org/write-less-do-more-with-javascript-es6-5fd4a8e50ee2). Les promesses nous permettent de gérer les requêtes asynchrones de manière plus intelligente. Voyons comment ==fetch== fonctionne techniquement.

![img code](https://cdn-media-1.freecodecamp.org/images/1*kz6k4VRs0RiVCasWR0pCow.png)

La fonction ==fetch== prend un paramètre obligatoire : l'URL du point de terminaison. Elle possède également d'autres paramètres facultatifs, comme dans l'exemple ci-dessous :

![img code](https://cdn-media-1.freecodecamp.org/images/1*QasrBgYZcU4BBFHqD2bBdg.png)

Comme vous pouvez le constater, ==fetch== présente de nombreux avantages pour effectuer des requêtes HTTP. Vous pouvez en apprendre davantage à son sujet ici. En outre, il existe dans fetch d'autres modules et plugins qui nous permettent d'envoyer et de recevoir une requête vers et depuis le serveur, comme axios.
## Axios

Axios est une bibliothèque open source permettant d'effectuer des requêtes HTTP et offre de nombreuses fonctionnalités intéressantes. Voyons comment elle fonctionne.

## Utilisation :

Tout d'abord, vous devez inclure Axios. Il y a deux façons d'inclure Axios dans votre projet.

Tout d'abord, vous pouvez utiliser npm :

```
npm install axios --save
```
Alors vous devez l'importer

```
import axios from 'axios'
```
Deuxièmement, vous pouvez inclure axios en utilisant un CDN.

```html
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
```
## Faire une requête avec Axios :
Avec Axios, vous pouvez utiliser ==GET== et ==POST== pour récupérer et envoyer des données depuis le serveur.

## GET :
![img code](https://cdn-media-1.freecodecamp.org/images/1*4wmqiPsSN5mdgjJiRaKVZg.png)
axios prend un paramètre obligatoire, et peut prendre un second paramètre optionnel aussi. Ceci prend des données comme une simple requête.

## POST:
![img code](https://cdn-media-1.freecodecamp.org/images/1*ey6-vwsrm9RAhyoU15u6xQ.png)

[Axios](https://github.com/axios/axios) renvoie une "Promesse". Si vous êtes familier avec les promesses, vous savez probablement qu'une promesse peut exécuter plusieurs requêtes. Vous pouvez faire la même chose avec axios et exécuter plusieurs requêtes en même temps.

![img code](https://cdn-media-1.freecodecamp.org/images/1*40Pji4utVKPpC7-dePfC6Q.png)

Axios prend en charge de nombreuses autres méthodes et options. Vous pouvez les explorer [ici](https://github.com/axios/axios).

## HttpClient d'Angular

Angular possède son propre module HTTP qui fonctionne avec les applications Angular. Il utilise la bibliothèque [RxJS](http://reactivex.io/rxjs/) pour gérer les requêtes asynchrones et propose de nombreuses options pour effectuer les requêtes HTTP.

## Appeler le serveur à l'aide du HttpClient d'Angular

Pour effectuer une requête à l'aide du HttpClient d'Angular, nous devons exécuter notre code dans une application Angular. J'en ai donc créé une. Si vous n'êtes pas familier avec Angular, consultez mon article, [apprenez à créer votre première application Angular en 20 minutes](https://medium.freecodecamp.org/learn-how-to-create-your-first-angular-app-in-20-min-146201d9b5a7).

La première chose à faire est d'importer ==HttpClientModule== dans ==app.module.ts==.

![img code](https://cdn-media-1.freecodecamp.org/images/1*iFuW5Fbp91VR5gwQ6XNMEQ.png)

Ensuite, nous devons créer un service pour gérer les demandes. Vous pouvez facilement générer un service en utilisant [Angular CLI](https://cli.angular.io/).

```
ng g service  FetchdataService
```

Ensuite, nous devons importer HttpClient dans le service ==fetchdataService.ts== et l'injecter dans le constructeur.

![img code](https://cdn-media-1.freecodecamp.org/images/1*kKwELAhSSpnN8DvIgdOfcQ.png)

Et dans ==app.component.ts== importer ==fetchdataService==

```ts
//import
import { FetchdataService } from './fetchdata.service';
```

Enfin, appelez le service et exécutez-le.

![img code](https://cdn-media-1.freecodecamp.org/images/1*OrRe183Yaclt19n5ZQ194Q.png)

Vous pouvez consulter l'exemple de démonstration sur [Stackblitz](https://stackblitz.com/edit/angular-httpclinent).

## Conclusion

Nous venons de couvrir les méthodes les plus courantes pour effectuer une demande d'appel HTTP en JavaScript.

Je vous remercie pour votre temps. Si vous aimez, applaudissez 50 fois, cliquez sur " suivre " et contactez-moi sur [Twitter](https://twitter.com/SaidHYN).

À propos, j'ai récemment travaillé avec un solide groupe d'ingénieurs logiciels pour l'une de mes applications mobiles. L'organisation était excellente et le produit a été livré très rapidement, bien plus rapidement que d'autres entreprises et indépendants avec lesquels j'ai travaillé. Je pense que je peux honnêtement les recommander pour d'autres projets. Envoyez-moi un courriel si vous voulez entrer en contact - [said@devsdata.com](said@devsdata.com).

Auteur: Said Hayani
Titre: Frontend Developer, Technical Writer, Bootcamp Instructor ➡️ Join my React/React Native class at nucamp.co and change your career in 6 months, use code F3748T ➡️ Get in touch info.said.dev@gmail.com 













