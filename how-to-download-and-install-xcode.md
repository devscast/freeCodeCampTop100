https://www.freecodecamp.org/news/how-to-download-and-install-xcode/

# Comment télécharger Xcode et l'installer sur votre Mac - et le mettre à jour pour le développement iOS


Xcode est l'outil utilisé par les développeurs pour créer des applications pour l'écosystème Apple - MacOS, iOS, et tout ce qui concerne Apple.

Ce guide vous expliquera comment installer Xcode sur votre Mac, du début à la fin.

Voici quelques conseils pratiques à connaître avant de commencer :

- Xcode ne fonctionne que sur un Mac. Si vous êtes sur un PC, vous ne pourrez malheureusement pas utiliser Xcode.
- Vous aurez besoin d'une bonne et stable connexion internet. La dernière version pèse environ 8 gigaoctets.
- Assurez-vous d'avoir au moins 30 gigaoctets d'espace libre sur votre ordinateur. Le dernier fichier .xip (v11.4.1 au moment de la rédaction) fait environ 8 gigaoctets compressés. Lorsque vous le décompressez, cela représente 17 gigaoctets supplémentaires. Ensuite, vous aurez besoin de l'outil en ligne de commande, ce qui représente 1,5 gigaoctet supplémentaire.

## Voici un aperçu des étapes à suivre pour installer Xcode

1. Télécharger Xcode
2. Installer l'outil de ligne de commande
3. Ouvrir la nouvelle version
4. Supprimer les fichiers

Notez que j'ai listé quelques commandes de Terminal dans les étapes ci-dessous. Ces commandes peuvent être tapées dans votre répertoire de travail actuel. Cela signifie que vous n'avez pas besoin de naviguer vers un dossier particulier.

Si vous le souhaitez vraiment, vous pouvez d'abord taper `cd` avant de taper les commandes dans les étapes ci-dessous. Cela vous ramènera au dossier d'origine.


## Option 1 : Télécharger la dernière version via l'App Store (ce n'est pas mon option préférée)

En théorie, ce processus devrait être transparent et sans douleur. Mais si l'installation échoue pour une raison quelconque à la dernière étape, il est très difficile de résoudre le problème.

Il existe plusieurs raisons d'échec, et il n'y a pas de moyen facile de savoir quelle est la cause sous-jacente. Si vous rencontrez un échec, vous devrez télécharger à nouveau l'ensemble du fichier à chaque fois que vous tenterez de résoudre le problème. Comme la dernière version fait 8 gigaoctets, je n'ai pas beaucoup apprécié cette approche.

Mais si vous vous sentez courageux, voici la marche à suivre :

* Ouvrez l'App Store sur votre Mac
* Connectez-vous
* Recherchez Xcode
* Cliquez sur installer ou mettre à jour

## Option 2 : Téléchargement via le site du développeur pour une version spécifique (mon option préférée)


1. Accédez à la section "plus" du [site Web des développeurs Apple](https://idmsa.apple.com/IDMSWebAuth/signin.html?path=%2Fdownload%2Fall%2F&appIdKey=891bd3417a7776362562d2197f89480a8547b108fd934911bcbea0110d07f757&rv=0).
2. Connectez-vous avec votre identifiant de compte iTunes
3. Saisissez la version que vous souhaitez et téléchargez le fichier `Xcode_x_x_x.xip`. N'oubliez pas que Xcode 11.4.1 pèse 8 gigaoctets, ce qui peut prendre un certain temps en fonction de votre connexion Internet.
4. Une fois le fichier téléchargé, cliquez sur `.xip` pour l'extraire. Votre ordinateur portable l'extraira dans le même dossier que celui où vous l'avez téléchargé. Ce processus d'extraction est automatique. Vous n'avez plus rien à faire après avoir cliqué sur le fichier `.xip`. Cette étape ne prendra que quelques minutes.
5. [Facultatif] Une fois extraite, renommez l'application en "Xcode11.x.x" si vous utilisez plusieurs versions.
Faites glisser l'application vers le dossier Applications
6. [Facultatif] Définissez la nouvelle version de Xcode comme la version par défaut. Ouvrez le Terminal et tapez `sudo xcode-select -switch /Applications/Xcodex.x.x.app` . Remplacez `x.x.x` par le numéro de la version. Par exemple : `Xcode11.4.1.app`. Vous devrez entrer le mot de passe administrateur de votre ordinateur. Je suis presque sûr que cela mettra à jour la version par défaut de Xcode pour tous les utilisateurs de votre ordinateur, donc le mieux est de vérifier avec d'autres utilisateurs d'abord.

## Étape 2 : installer l'outil de ligne de commande (CLT)
Si vous avez plusieurs utilisateurs sur votre ordinateur, vous devrez mettre à jour le CLT pour chaque utilisateur.

Téléchargez le fichier `.dmg`

Pour mettre à jour le CLT, [allez sur le site du développeur](https://idmsa.apple.com/IDMSWebAuth/signin?appIdKey=891bd3417a7776362562d2197f89480a8547b108fd934911bcbea0110d07f757&path=%2Fdownload%2Fmore%2F&rv=1) d'applications et téléchargez l'outil de ligne de commande `.dmg`.

Si vous n'avez jamais installé Xcode auparavant, vous pourrez peut-être effectuer la mise à jour avec votre Terminal en tapant `xcode-select --install` au lieu de vous rendre sur le site du développeur.

Mais si vous avez une version existante de Xcode installée sur votre machine, vous verrez probablement cette erreur :

```
xcode-select: error: command line tools are already installed, use “Software Update” to install updates
```

Vous devrez donc vous rendre sur le site Web du développeur.

## Installation de la CLT

Lorsque le téléchargement du `.dmg` est terminé, double-cliquez sur le fichier pour l'ouvrir. Cela ouvrira une petite fenêtre qui ressemble à ceci :

Double-cliquez sur la boîte et suivez les instructions pour installer le CLT. L'installation prendra quelques minutes.

À la fin de l'installation, il se peut que le logiciel vous demande si vous souhaitez le mettre à la corbeille. Dans ce cas, il s'agit de déplacer le fichier `.dmg` vers la corbeille. Puisque vous ne devriez plus avoir besoin de ce fichier. Je dis toujours oui à cela.

## Étape 3 : Ouvrir Xcode

Ouvrez le dossier Applications et ouvrez la nouvelle version de Xcode. Si vous avez renommé Xcode, assurez-vous d'ouvrir la bonne application.

Xcode peut vous demander d'installer des composants supplémentaires. Cliquez sur installer. Cela prendra quelques minutes.


Pendant l'installation, vérifiez que votre version de Xcode par défaut est celle que vous venez de télécharger :

* Ouvrez un terminal
* Tapez brew config
*  Vous devriez voir les versions "CLT" et "Xcode", ainsi que tout le reste. Cela devrait refléter la version que vous venez de télécharger. Dans mon cas, j'ai téléchargé Xcode 11.4.1.


```
CLT: 11.4.1.0.1.1586360307
Xcode: 11.4.1 => /Applications/Xcode11.4.1.app/Contents/Developer
```

Une fois les composants installés, Xcode se lancera. Vous devriez pouvoir reprendre vos anciens projets et continuer là où vous vous êtes arrêté sans problème*.

*Notez que si vous utilisez des outils proxy, tels que Charles, vous devrez réinstaller ces certificats dans votre simulateur.

Si vous rencontrez des erreurs en essayant de construire ou d'exécuter un projet, vérifiez quel dispositif vous essayez de lancer. La nouvelle version peut ne pas se souvenir du dispositif que vous utilisiez auparavant. Si c'est le cas, cliquez sur le dispositif et choisissez "Ajouter des simulateurs supplémentaires" dans le menu déroulant pour ajouter le dispositif que vous voulez.

## Étape 4. Supprimez les fichiers

Si vous n'avez pas besoin des anciennes versions de Xcode sur votre ordinateur, vous pouvez les désinstaller et récupérer de l'espace sur votre disque dur.

Vous pouvez également supprimer le fichier `.xip` de la version que vous venez de télécharger, ainsi que le fichier `CLT.dmg`.

Voilà, c'est tout. J'espère que cela vous a aidé à installer Xcode avec succès. Amusez-vous bien avec !
