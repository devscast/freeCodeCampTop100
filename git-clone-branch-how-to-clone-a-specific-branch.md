https://www.freecodecamp.org/news/git-clone-branch-how-to-clone-a-specific-branch/

# Git Clone Branch - Comment cloner une branche spécifique

***Contrairement aux anciens systèmes de contrôle de version centralisés tels que SVN et CVS, Git est distribué. Chaque développeur dispose de l'historique complet et du contrôle de son code, localement ou à distance. Il peut également accéder à plusieurs parties du code ou les manipuler comme bon lui semble à partir de différents endroits.***

Depuis que Linus Torvalds (le célèbre créateur du noyau du système d'exploitation Linux) a créé Git en 2005 pour le développement du noyau Linux, il est devenu le système de contrôle de version moderne le plus utilisé dans le monde.

Dans cet article, je vous présenterai les flux de travail Git clone et Git branche et je vous montrerai comment cloner une branche spécifique en fonction de vos besoins. C'est parti ! ?

## Conditions préalables

* Connaissance de base du terminal
* Capacité à taper des commandes dans le terminal
* Git installé (je vous montrerai quand même comment)
* Un compte GitHub
* Un sourire sur votre visage (affichez ce sourire l'ami ?)

## Introduction rapide à Git et GitHub
Selon [Wikipedia](https://en.wikipedia.org/wiki/Git),

> ***Git*** est un système de contrôle de version distribué conçu pour suivre les modifications apportées à un projet (code) dans le cadre du développement de logiciels. Il est destiné à renforcer la coordination, la collaboration, la rapidité et l'efficacité entre les développeurs.
***GitHub***, quant à lui, est un service d'hébergement basé sur le Web pour le contrôle de version à l'aide de Git. Il offre toutes les fonctionnalités de contrôle de version distribué et de gestion du code source de Git, tout en ajoutant des fonctionnalités supplémentaires pour le code informatique.


## Comment installer Git sous Windows

Téléchargez et installez la dernière version du programme d'installation de [Git pour Windows ici](https://gitforwindows.org/).

## Comment installer Git sous Linux

Voici les commandes en fonction de votre distro Linux :

### Debian ou Ubuntu

```bash
sudo apt-get update
sudo apt-get install git
```

### Fedora

```bash
sudo dnf install git
```

### CentOS

```bash
sudo yum install git
```

### Arch Linux

```bash
sudo pacman -Sy git
```

### Gentoo

```bash
sudo emerge --ask --verbose dev-vcs/git
```

## Comment installer Git sur un Mac

Téléchargez et installez la dernière version du programme d'installation de [Git pour Mac ici](https://sourceforge.net/projects/git-osx-installer/files/).

Ou vous pouvez taper cette commande :

```bash
brew install git
```

Maintenant que nous avons installé Git, passons au tutoriel.

## Introduction à Git Clone

Git vous permet de gérer et de versionner votre ou vos projets dans un "dépôt". Ce dépôt est stocké sur un service d'hébergement web pour le contrôle de version, comme GitHub.

Vous pouvez ensuite cloner ce dépôt sur votre machine locale et disposer de tous les fichiers et branches en local (je vous expliquerai plus en détail les branches prochainement).

Par exemple, vous pouvez cloner le dépôt de freeCodeCamp avec SSH comme suit :

```bash
git clone git@github.com:freeCodeCamp/freeCodeCamp.git
```

## Introduction aux branches de Git

Lorsque vous travaillez sur un projet, vous aurez probablement différentes fonctionnalités. Et plusieurs contributeurs travailleront sur ce projet et ses fonctionnalités.

Les branches vous permettent de créer un "terrain de jeu" avec les mêmes fichiers que ceux de la branche ```master```. Vous pouvez utiliser cette branche pour créer des fonctionnalités indépendantes, tester de nouvelles fonctionnalités, apporter des modifications, créer des correctifs, rédiger des documents ou tester des idées sans casser ou affecter le code de production. Lorsque vous avez terminé, vous fusionnez la branche avec la branche ```master``` de production.

Le branchement est un concept fondamental de Git, qui est également utilisé dans GitHub pour gérer les flux de travail des différentes versions d'un projet. La branche ```master``` est toujours la branche par défaut dans un dépôt qui est le plus souvent considéré comme du "code de production et déployable". De nouvelles branches comme ```passwordless-auth``` ou ```refactor-signup-ux``` peuvent être créées à partir de la branche ```master```.

## Comment cloner des branches Git

Bien que vous puissiez cloner des dépôts avec la commande ```git clone```, gardez à l'esprit que cela clone la branche et le ```HEAD``` distant. Ce dernier est généralement le ```master``` par défaut et inclut toutes les autres branches du dépôt.

Ainsi, lorsque vous clonez un dépôt, vous clonez ```le master``` et toutes les autres branches. Cela signifie que vous devrez vérifier une autre branche vous-même.

Disons que votre tâche sur un projet est de travailler sur une fonctionnalité pour ajouter l'authentification sans mot de passe à un tableau de bord utilisateur. Et cette fonctionnalité se trouve dans la branche ```passwordless-auth```.

Vous n'avez pas vraiment besoin de la branche ```master``` puisque votre "branche de fonctionnalité" sera fusionnée dans ```master``` par la suite. Comment alors cloner cette branche ```passwordless-auth``` sans aller chercher toutes les autres branches avec "un tas de fichiers dont vous n'avez pas besoin" ?

J'ai créé ce dépôt d'exemple pour expliquer cela. Ce dépôt contient un blog simple construit avec Nextjs et a quatre branches fictives :

* master
* dev
* staging
* passwordless-auth

Dans Nextjs, tout fichier à l'intérieur du dossier `pages/api` est mappé au chemin `/api/*` et sera traité comme un endpoint API au lieu d'une `page`. Dans notre référentiel, j'ai créé différentes API [fictives dans ce répertoire](https://github.com/BolajiAyodeji/nextjs-blog/tree/master/pages/api) pour que chaque branche soit différente.

La branche `master` contient le fichier ***pages/api/hello.js*** tandis que `passwordless-auth` contient le fichier ***pages/api/auth.js***. Chaque fichier renvoie simplement une réponse textuelle factice. Voyez la réponse API hello de `master` [ici](https://nextjs-blog.bolajiayodeji.vercel.app/api/hello) (avec un message spécial pour vous ?).

Clonons le dépôt :

```bash
git clone git@github.com:BolajiAyodeji/nextjs-blog.git
```

Cela nous donne accès à toutes les branches de ce dépôt et vous pouvez facilement passer de l'une à l'autre pour voir chaque version et ses fichiers.

```bash
git branch -a
```

Vous vous demandez d'où viennent les branches **remotes/origin/...** ?

Lorsque vous clonez un dépôt, vous tirez des données d'un dépôt sur Internet ou d'un serveur interne appelé **remote**. Le mot origine est un alias créé par votre Git pour remplacer l'URL distant (vous pouvez changer ou spécifier un autre alias si vous le souhaitez).

Ces branches **remotes/origin/...** vous ramènent au dépôt d'origine que vous avez cloné depuis l'internet afin que vous puissiez toujours effectuer des pull/push depuis l'origine.

Ainsi, lorsque vous clonez **master** sur votre machine, **remotes/origin/master** est la branche **master** originale sur Internet, et **master** est sur votre machine locale. Vous allez donc tirer et pousser depuis et vers **remotes/origin/master**.

En résumé, **Remote** est l'URL qui pointe vers le dépôt sur Internet, tandis que **Origin** est un alias pour cette URL distante.


## Comment cloner une branche spécifique

Maintenant, nous allons cloner une branche spécifique de notre dépôt de démonstration. Il y a deux façons de cloner une branche spécifique. Vous pouvez soit :

* Cloner le référentiel, récupérer toutes les branches, et extraire vers une branche spécifique immédiatement.
* Cloner le référentiel et récupérer une seule branche.

### Première option

```bash 
git clone --branch <branchname> <remote-repo-url>
```
ou 

```bash 
git clone -b <branchname> <remote-repo-url>
```

Here **-b** is just an alias for **--branch** 

Avec cela, vous récupérez toutes les branches du dépôt, vous vérifiez celle que vous avez spécifiée, et la branche spécifique devient la branche locale configurée pour **git push** et **git pull** . Mais vous récupérez toujours tous les fichiers de chaque branche. Ce n'est peut-être pas ce que vous voulez, n'est-ce pas ? ?

Testons-le :

```bash 
git clone -b passwordless-auth git@github.com:BolajiAyodeji/nextjs-blog.git
```

Cela configure automatiquement ``passwordless-auth`` en tant que branche locale mais permet de suivre les autres branches.


Deuxième option

```bash 
git clone --branch <branchname> --single-branch <remote-repo-url>
```

ou 

```bash 
git clone -b <branchname> --single-branch <remote-repo-url>
```

Cette option effectue la même action que l'option 1, sauf que l'option ``--single-branch`` a été introduite dans Git version 1.7.10 et suivantes. Elle permet de récupérer uniquement les fichiers de la branche spécifiée sans récupérer les autres branches.

Testons-la :

```bash 
git clone -b passwordless-auth --single-branch git@github.com:BolajiAyodeji/nextjs-blog.git
```

Cela configure automatiquement ```passwordless-auth``` comme la branche locale et ne suit que cette branche.

Si vous exécutez ``cd pages/api``, vous trouverez le fichier ``auth.js`` dans la branche ```passwordless-auth``` comme prévu par la configuration précédente.


## Conclusion

Vous pouvez être à court d'internet ou d'espace de stockage mais vous devez travailler sur une tâche dans une branche spécifique. Ou vous pouvez vouloir cloner une branche spécifique avec des fichiers limités pour diverses raisons. Heureusement, Git vous offre la flexibilité de le faire. Exercez vos muscles et essayez, il y a beaucoup plus de "Git" à apprendre.

Un par un, d'accord ? ✌ ?