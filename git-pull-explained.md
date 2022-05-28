# Git Pull expliqué

![image cover](https://www.freecodecamp.org/news/content/images/size/w2000/2020/02/clem-onojeghuo-gBnHMsAOWrs-unsplash.jpg)

    git pull est une commande Git utilisée pour mettre à jour la version locale d'un dépôt à partir d'un dépôt distant.

C'est l'une des quatre commandes qui incite à l'interaction avec le réseau par Git. Par défaut, ==git pull== fait deux choses.

+ met à jour la branche de travail locale actuelle (branche actuellement extraite)
+ met à jour les branches de suivi distantes pour toutes les autres branches.

==git pull== récupère (==git fetch==) les nouveaux commits et les fusionne ([git merge](https://guide.freecodecamp.org/git/git-merge)) dans votre branche locale.

La syntaxe de cette commande est la suivante :

```git
# General format
git pull OPTIONS REPOSITORY REFSPEC

# Pull from specific branch
git pull REMOTE-NAME BRANCH-NAME
```

dans laquelle :

+ OPTIONS sont les options de la commande, telles que ==--quiet== ou ==--verbose==. Vous pouvez en savoir plus sur les différentes options dans la [documentation de Git](https://git-scm.com/docs/git-pull).
+ REPOSITORY est l'URL de votre repo. Exemple : https://github.com/freeCodeCamp/freeCodeCamp.git
+ REFSPEC spécifie les références à récupérer et les références locales à mettre à jour.
+ REMOTE-NAME est le nom de votre dépôt distant. Par exemple : origin.
+ BRANCH-NAME est le nom de votre branche. Par exemple : develop.

Note

Si vous avez des modifications non validées, la partie fusion de la commande ==git pull== échouera et votre branche locale ne sera pas touchée.

Ainsi, vous devriez toujours commiter vos changements dans une branche avant de tirer de nouveaux commits d'un repository distant.

Table des matières

+ Utilisation de ==[git pull](https://guide.freecodecamp.org/git/git-pull/#using-git-pull)==
+ Contrôle de version distribué
+ [==git fetch==  ==git merge==](https://guide.freecodecamp.org/git/git-pull/#git-fetch-plus-git-merge)
+ [==git pull== dans les IDE](https://guide.freecodecamp.org/git/git-pull/#git-pull-in-IDEs)

# Utiliser git pull

Utilisez ==git pull== pour mettre à jour un dépôt local à partir du dépôt distant correspondant. Ex : Pendant que vous travaillez localement sur ==master==, exécutez ==git pull== pour mettre à jour la copie locale de ==master== et mettre à jour les autres branches de suivi distantes. (Plus d'informations sur les branches de suivi à distance dans la section suivante).

Mais, il y a quelques choses à garder à l'esprit pour que cet exemple soit vrai :

Le dépôt local a un dépôt distant lié.

+ Vérifiez-le en exécutant ==git remote -v==
+ S'il y a plusieurs dépôts distants, ==git pull== peut ne pas être une information suffisante. Vous pouvez avoir besoin d'entrer ==git pull origin== ou ==git pull upstream==.

La branche sur laquelle vous êtes actuellement extrait a une branche de suivi distante correspondante.

+ Vérifiez-le en exécutant ==git status==. S'il n'y a pas de branche de suivi à distance, Git ne sait pas d'où tirer les informations.

# Contrôle de version distribué

Git est un **système de contrôle de version distribué** (DVCS). Avec DVCS, les développeurs peuvent travailler sur le même fichier au même moment dans des environnements distincts. Après avoir poussé le code vers le dépôt distant partagé, les autres développeurs peuvent récupérer le code modifié.

# Interactions avec le réseau dans Git

Il n'y a que quatre commandes qui permettent des interactions réseau dans Git. Un dépôt local n'a pas connaissance des changements effectués sur le dépôt distant tant qu'il n'y a pas de demande d'information. De même, un dépôt distant n'a pas connaissance des changements locaux tant que les commits ne sont pas poussés.

Les quatre commandes de réseau sont :
+ ==git clone==
+ ==git fetch==
+ ==git pull==
+ ==git push==

# Branches dans DVCS

Lorsque l'on travaille avec Git, on peut avoir l'impression qu'il y a beaucoup de copies du même code qui flottent un peu partout. Il y a différentes versions du même fichier sur chaque branche. Et, différentes copies des mêmes branches sur l'ordinateur de chaque développeur et sur le serveur distant. Pour garder la trace de tout cela, Git utilise quelque chose appelé **branches de suivi à distance**.

Si vous exécutez ==git branch --all== dans un dépôt Git, les branches de suivi à distance apparaissent en rouge. Ce sont des copies en lecture seule du code tel qu'il apparaît sur le serveur distant. ( A quand remonte la dernière interaction réseau qui aurait apporté des informations localement ? Rappelez-vous quand ces informations ont été mises à jour pour la dernière fois. Les informations dans les branches de suivi à distance reflètent les informations de cette interaction).

Avec les **branches de suivi à distance**, vous pouvez travailler dans Git sur plusieurs branches sans interaction avec le réseau. Chaque fois que vous exécutez les commandes ==git pull== ou ==git fetch==, vous mettez à jour les branches de suivi à distance.

# git fetch plus git merge

==git pull== est une commande combinée, égale à ==git fetch== + ==git merge==.

# git fetch

Par lui-même, ==git fetch== met à jour toutes les branches de suivi distantes dans le dépôt local. Aucun changement n'est réellement reflété sur aucune des branches de travail locales.

# git merge

Sans aucun argument, ==git merge== fusionnera la branche de suivi distante correspondante à la branche de travail locale.

# git pull

==git fetch== met à jour les branches de suivi à distance. ==git merge== met à jour la branche courante avec la branche de suivi à distance correspondante. En utilisant ==git pull==, vous obtenez les deux parties de ces mises à jour. Mais, cela signifie que si vous êtes en checkout sur la branche ==feature== et que vous exécutez ==git pull==, lorsque vous faites un checkout sur ==master==, les nouvelles mises à jour ne seront pas incluses. Chaque fois que vous faites un checkout vers une autre branche qui peut avoir de nouveaux changements, c'est toujours une bonne idée d'exécuter ==git pull==.

# git pull dans les IDE

Le langage courant dans d'autres IDES peut ne pas inclure le mot ==pull==. Si vous cherchez les mots ==git pull== mais ne les voyez pas, cherchez le mot ==sync== à la place.

# Récupérer une PR (Pull Request) distante dans le repo local

Pour des raisons de révision et autres, les PRs à distance doivent être récupérées dans le repo local. Pour ce faire, vous pouvez utiliser la commande ==git fetch== de la manière suivante.

==git fetch origin pull/ID/head:BRANCHNAME==

ID est l'identifiant de la demande de pull et BRANCHNAME est le nom de la branche que vous voulez créer. Une fois que la branche a été créée, vous pouvez utiliser ==git checkout== pour passer à cette branche.

# Autres ressources sur git dans guide.freecodecamp.org

+ [Fusion de Git](https://guide.freecodecamp.org/git/git-merge/index.md)
+ [Git checkout](https://guide.freecodecamp.org/git/git-checkout/index.md)
+ [Git commit](https://guide.freecodecamp.org/git/git-commit/index.md)
+ [Git stash](https://guide.freecodecamp.org/git/git-stash/index.md)
+ [Branche de Git](https://guide.freecodecamp.org/git/git-branch/index.md)

