https://www.freecodecamp.org/news/git-fetch-vs-pull/

# Git Fetch vs Pull : quelle est la différence entre les commandes Git Fetch et Git Pull ?

<p  align="center">
Git `pull` et `fetch` sont deux commandes qui sont régulièrement utilisées par les utilisateurs de Git. Voyons la différence entre ces deux commandes.
</p>


Pour des raisons de contexte, il est bon de rappeler que nous travaillons probablement dans un repo clone. Qu'est-ce qu'un clone ? Il s'agit simplement d'une duplication d'un autre dépôt. Il s'agit en fait d'obtenir votre propre copie du code source de quelqu'un d'autre.

Cela dit, pour garder votre clone à jour avec les changements qui ont été appliqués à l'original, vous devez les apporter à votre clone.

C'est là que `fetch` et `pull` interviennent.

`git fetch` est la commande qui indique à votre git local de récupérer les dernières informations de méta-données de l'original (mais ne fait aucun transfert de fichiers). C'est plutôt une vérification pour voir s'il y a des changements disponibles) .

`git pull,` d'un autre côté, fait cela ET apporte (copie) ces changements depuis le dépôt distant.

Par exemple :

```
git pull origin ankur bugfix
```
Il faut garder à l'esprit qu'il y a généralement au moins trois copies d'un projet sur votre poste de travail.

- Une copie est votre propre dépôt avec votre propre historique de livraison (la copie déjà enregistrée, pour ainsi dire).

- La deuxième copie est votre copie de travail où vous éditez et
  construisez (pas encore livrée à votre dépôt).

- La troisième copie est votre copie locale "en cache" d'un dépôt distant (probablement l'original à partir duquel vous avez cloné le vôtre).

Vous pouvez utiliser `git fetch` pour connaître les changements effectués dans le repo/branche distant depuis votre dernier pull. Ceci est utile pour permettre une vérification avant de faire un pull réel, qui pourrait changer les fichiers dans votre branche actuelle et votre copie de travail (et potentiellement perdre vos changements, etc).

```
git fetch    
git diff ...origin
```

Si cet article vous a aidé, [Faites un tweet](https://twitter.com/intent/tweet?text=Git%20Fetch%20vs%20Pull%3A%20What%27s%20the%20Difference%20Between%20the%20Git%20Fetch%20and%20Git%20Pull%20Commands%3F%0A%0Ahttps://www.freecodecamp.org/news/git-fetch-vs-pull/)

Apprenez à coder gratuitement. Le programme open source de freeCodeCamp a aidé plus de 40 000 personnes à trouver un emploi de développeur. [Commencer](https://www.freecodecamp.org/learn)