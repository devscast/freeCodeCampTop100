https://www.freecodecamp.org/news/how-to-undo-a-git-add/

https://www.freecodecmap.fr/nouvelles/comment-annuler-un-ajout-git

# Comment annuler un ajout Git ?

Pour annuler `git add` avant un commit, exécutez `git reset <file>` ou `git reset` pour annuler toutes les modifications.

Dans les anciennes versions de Git, les commandes étaient respectivement `git reset HEAD <file>` et `git reset HEAD`. Ceci a été modifié dans Git 1.8.2

Vous pouvez en savoir plus sur d'autres actions Git couramment utilisées dans ces articles utiles :

- [Git checkout](https://guide.freecodecamp.org/git/git-checkout/)
- [Git pull vs Git fetch](https://guide.freecodecamp.org/miscellaneous/git-pull-vs-git-fetch/)
- [Gitignore](https://guide.freecodecamp.org/git/gitignore/)

## Voici un peu plus d'informations de base sur Git
### Comprendre les trois sections d'un projet Git

Un projet Git aura les trois sections principales suivantes :

1. Répertoire Git
2. Répertoire de travail (ou arbre de travail)
3. Zone de transit

Le **répertoire Git** (situé dans `VOTRE-PROJET-PATH/.git/`) est l'endroit où Git stocke tout ce dont il a besoin pour suivre le projet avec précision. Cela inclut les métadonnées et une base de données d'objets qui comprend les versions compressées des fichiers du projet.

Le **répertoire de travail** est l'endroit où un utilisateur apporte des modifications locales à un projet. Le répertoire de travail extrait les fichiers du projet de la base de données des objets du répertoire Git et les place sur la machine locale de l'utilisateur.

La **zone de transit** est un fichier (également appelé "index", "stage", ou "cache") qui stocke des informations sur ce qui sera intégré dans votre prochain commit. Un commit est le moment où vous demandez à Git de sauvegarder ces changements. Git prend un instantané des fichiers tels qu'ils sont et stocke définitivement cet instantané dans le répertoire Git.

Avec trois sections, il y a trois états principaux dans lesquels un fichier peut se trouver à un moment donné : validé (committed), modifié (modified) ou mis à disposition (staged). Vous modifiez un fichier chaque fois que vous y apportez des changements dans votre répertoire de travail. Ensuite, il est mis à disposition lorsque vous le déplacez vers la zone de mise à disposition. Enfin, il est livré après un commit.

## Installer Git
- Ubuntu: `sudo apt-get install git`
- Windows: [Download](https://git-scm.com/download/win)
- Mac: [Download](https://git-scm.com/download/mac)


## Configurer l'environnement Git
Git possède un outil `git config` qui vous permet de personnaliser votre environnement Git. Vous pouvez modifier l'apparence et le fonctionnement de Git en définissant certaines variables de configuration. Exécutez ces commandes à partir d'une interface de ligne de commande sur votre machine (Terminal sous Mac, Command Prompt ou Powershell sous Windows).

Il existe trois niveaux d'emplacement pour ces variables de configuration :

1. Système : situé dans `/etc/gitconfig`, applique les paramètres par défaut à chaque utilisateur de l'ordinateur. Pour apporter des modifications à ce fichier, utilisez l'option --system avec la commande git config.

2. User : situé dans `~/.gitconfig` ou `~/.config/git/config`, applique les paramètres à un seul utilisateur. Pour apporter des modifications à ce fichier, utilisez l'option --global avec la commande git config.

3. Projet : situé dans `VOTRE-PROJET-PATH/.git/config`, applique les paramètres au projet uniquement. Pour apporter des modifications à ce fichier, utilisez la commande git config.

Si certains paramètres entrent en conflit les uns avec les autres, les configurations au niveau du projet prévaudront sur celles au niveau de l'utilisateur, et les configurations au niveau de l'utilisateur prévaudront sur celles au niveau du système.

**Note pour les utilisateurs de Windows** : Git recherche le fichier de configuration de niveau utilisateur (`.gitconfig`) dans votre répertoire `$HOME` (`C:\Users\$USER`). Git recherche également le fichier `/etc/gitconfig`, bien qu'il soit relatif à la racine MSys, qui est l'endroit où vous décidez d'installer Git sur votre système Windows lorsque vous exécutez le programme d'installation. Si vous utilisez la version 2.x ou ultérieure de Git pour Windows, il existe également un fichier de configuration au niveau du système dans `C:\Documents and Settings\All Users\Application Data\Git\config` sous Windows XP, et dans `C:\ProgramData\Git\config` sous Windows Vista et plus récent. Ce fichier de configuration ne peut être modifié que par `git config -f FICHIER` en tant qu'administrateur.

## Ajouter votre nom et votre email
Git inclut le nom d'utilisateur et l'email dans les informations d'un commit. Vous devez configurer ces informations dans votre fichier de configuration de niveau utilisateur à l'aide de ces commandes :

```bash
git config --global user.name "Mon Nom"
git config --global user.email "monemail@example.com"
```

## Changer votre éditeur de texte
Git utilise automatiquement votre éditeur de texte par défaut, mais vous pouvez le modifier. Voici un exemple pour utiliser l'éditeur Atom à la place (l'option `--wait` indique au shell d'attendre l'éditeur de texte pour que vous puissiez y travailler avant que le programme ne passe à autre chose) :

```bash
git config --global core.editor "atom --wait"
```

## Ajouter de la couleur à la sortie de Git
Vous pouvez configurer votre shell pour ajouter de la couleur à la sortie de Git avec cette commande :

```
git config --global color.ui true
```

Pour voir tous vos paramètres de configuration, utilisez la commande `git config --list`.

## Initialiser Git dans un projet
Une fois que Git est installé et configuré sur votre ordinateur, vous devez l'initialiser dans votre projet pour commencer à utiliser ses pouvoirs de contrôle de version. Dans la ligne de commande, utilisez la commande cd pour naviguer vers le dossier de premier niveau (ou racine) de votre projet. Ensuite, exécutez la commande git init. Ceci installe un dossier répertoire Git avec tous les fichiers et objets dont Git a besoin pour suivre votre projet.

Il est important que le répertoire Git soit installé dans le dossier racine du projet. Git peut suivre les fichiers dans les sous-dossiers, mais il ne suivra pas les fichiers situés dans un dossier parent relatif au répertoire Git.

## Obtenir de l'aide dans Git
Si vous oubliez comment fonctionne une commande dans Git, vous pouvez accéder à l'aide de Git depuis la ligne de commande de plusieurs façons :

```bash
git help COMMAND
git COMMAND --help
man git-COMMAND
```

Ceci affiche la page de manuel de la commande dans votre fenêtre shell. Pour naviguer, faites défiler avec les touches fléchées haut et bas ou utilisez les raccourcis clavier suivants :

f ou barre d'espace pour avancer
b pour revenir en arrière
q pour quitter
