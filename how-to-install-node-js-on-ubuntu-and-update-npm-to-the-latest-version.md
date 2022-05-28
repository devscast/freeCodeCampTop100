https://www.freecodecamp.org/news/how-to-install-node-js-on-ubuntu-and-update-npm-to-the-latest-version/

# Comment installer Node.js sur Ubuntu et mettre à jour npm à la dernière version

### Si vous essayez d'installer la dernière version de Node à l'aide du gestionnaire de paquets apt, vous obtiendrez la version **10.19.0.** C'est la dernière version dans l'ubuntu app store, mais ce n'est pas la dernière version publiée de NodeJS.

En effet, lorsque de nouvelles versions d'un logiciel sont publiées, il faut parfois plusieurs mois à l'équipe Ubuntu pour les tester et les publier dans la boutique officielle Ubuntu. Par conséquent, pour obtenir les dernières versions d'un logiciel, nous devons parfois utiliser des paquets privés publiés par les développeurs.

Dans ce tutoriel, ce que nous voulons faire est d'obtenir soit la **v12.18.1** (LTS - avec Long term support) ou la v14.4 de Node. Pour obtenir les dernières versions, nous pouvons utiliser soit **nodesource** soit **nvm** (node version manager). Je vais vous montrer comment utiliser les deux.

Toutes les commandes ici seront exécutées en utilisant le CLI/terminal d'Ubuntu.

## Utilisation de NVM - ma méthode préférée

J'aime le nvm car il me permet d'utiliser différentes versions de node pour différents projets.
Parfois, vous pouvez collaborer sur un projet avec quelqu'un qui utilise une version différente de node et vous devez changer de version de node pour répondre aux besoins du projet. Pour cela, nvm est le meilleur outil.

## Installer NVM
`curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash`

Pour vérifier que nvm est installé, tapez `nvm --version`. Si vous obtenez un numéro de version comme `0.35.3`, alors vous savez que nvm a été installé avec succès.

Redémarrez votre terminal pour que vos changements prennent effet.

## Installer NodeJS

Ensuite, nous allons installer la version 14.4 de Nodejs.

Exécutez simplement `nvm install 14.4.0 .`

Vous pouvez utiliser une commande similaire pour installer n'importe quelle version de node que vous voulez, par exemple `nvm install 12.18.1.`

Cette commande installe automatiquement nodejs ainsi que la dernière version de npm qui est à `v6.14.5.`

Si jamais vous avez besoin de changer de version de node, vous pouvez simplement exécuter nvm use <version-number> , par exemple nvm use `v12.18.1.`

Pour lister les différentes versions de node que vous avez installées avec nvm, exécutez `nvm ls.`

## Installer Nodesource
Exécutez la commande ci-dessous pour indiquer à Ubuntu que nous voulons installer le paquetage Nodejs à partir de nodesource.

`curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -`

**NB** que `v14.4.0` est la dernière version de Node mais n'a pas actuellement de LTS - support à long terme fourni pour elle. Pour installer la dernière version de Node avec LTS, changez **`14`** dans la commande ci-dessus en `12`.

Vous pouvez être invité à entrer le mot de passe de votre utilisateur root. Entrez-le et appuyez sur entrée/retour.

## Installer NodeJS

Une fois que nous avons fini de configurer Nodesource, nous pouvons maintenant installer Nodejs v14.4.
Exécutez `sudo apt-get install -y nodejs`.

Une fois que nous avons terminé, nous pouvons vérifier que nous avons la dernière version de Node installée.
Tapez simplement `nodejs -v` dans votre terminal et il devrait retourner `v14.4.0`.

Npm devrait être automatiquement installé à ce stade. Pour vérifier quelle version de npm vous avez, exécutez `npm version`. Si vous n'obtenez pas un objet qui inclut la dernière version de `npm à 6.14.5, { npm : '6.14.5' }`, vous pouvez mettre à jour npm manuellement en exécutant la commande suivante :

`npm install -g npm@latest.`

Si vous rencontrez des problèmes avec npm qui ne peut pas se mettre à jour parce qu'il n'est pas installé, vous pouvez d'abord installer npm en utilisant `sudo apt-get install -y npm`, puis exécuter la commande ci-dessus pour le mettre à jour.

Pour que certains paquets npm fonctionnent, nous devons également exécuter la commande suivante
`sudo apt install build-essential.`

Et voilà, c'est fait !

Vous avez les dernières versions de NodeJS et NPM sur votre machine Ubuntu.

Allez construire de bons produits :)
