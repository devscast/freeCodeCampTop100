https://www.freecodecamp.org/news/how-to-configure-your-macos-terminal-with-zsh-like-a-pro-c0ab3f3c1156/

# Comment configurer votre terminal macOs avec Zsh comme un pro

Parfois, l'utilisation du terminal par défaut craint. Vous voulez sortir de l'ordinaire, ajouter de la vie au terminal ennuyeux et améliorer votre productivité.

[Z shell](https://en.wikipedia.org/wiki/Z_shell) (Zsh) est un shell Unix construit au-dessus de bash (le shell par défaut de macOS) avec un grand nombre d'améliorations.

Dans cette présentation, nous allons configurer iTerm2 avec ZSH et ses dépendances. C'est une évidence, et après cela, vous vous demanderez pourquoi vous n'avez pas découvert ZSH plus tôt. Eh bien, puisque vous êtes déjà là, commençons par le début.

### Keynotes

* Installation Homebrew
* Installation d'iTerm2
* Installations de ZSH et Oh My ZSH
* Mise en place des dépendances pour créer un beau terminal

### Étape 1 : Installer Homebrew

[Homebrew](https://brew.sh/) est un système de gestion de paquets logiciels gratuit et open-source qui simplifie l'installation de logiciels sur macOS d'Apple.

Avant d'installer Homebrew, nous devons installer les outils CLI pour Xcode. Ouvrez votre terminal et exécutez la commande :

```bash
xcode-select —-install
```
Si vous obtenez une erreur, exécutez `xcode-select -r` pour réinitialiser `xcode-select`.
Ensuite, installez Homebrew.

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Étape 2 : Installer iTerm2

iTerm2 est un remplacement du terminal et le successeur d'iTerm. La plupart des ingénieurs logiciels préfèrent [iTerm2 ](https://iterm2.com/)
au terminal par défaut fourni avec macOS en raison de [ses fonctionnalités intéressantes](https://iterm2.com/features.html). Vous pouvez intégrer zsh à 
iTerm2 pour augmenter votre productivité.

Pour installer iTerm2, exécutez la commande :

```bash
brew cask install iterm2
```
### Étape 3 : Installer ZSH
> Zsh est un shell conçu pour une utilisation interactive, 
> bien qu'il soit également un puissant langage de script.

Par défaut, macOs est livré avec zsh situé dans `/bin/zsh`.

Installons zsh en utilisant brew et faisons en sorte que iTerm2 l'utilise.

```bash 
brew install zsh
```

### Étape 4 : Installer Oh My Zsh

> "Oh My Zsh est un cadre open source, dirigé par la communauté, pour gérer votre configuration [zsh](https://www.zsh.org/). 
> Il ne fera pas de vous un développeur 10x... mais vous pourrez vous sentir comme tel".

> Robby Russell

Il fonctionne sur Zsh pour fournir des fonctionnalités cool configurables dans le fichier de 
configuration ~/.zhrc. Installez [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh) en exécutant la commande

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Vérifiez la version installée

```bash
zsh --version
```

Vous pouvez le mettre à niveau pour bénéficier des dernières fonctionnalités qu'il offre.

```bash
upgrade_oh_my_zsh
```

Redémarrez iTerm2 pour plonger dans la nouvelle expérience de l'utilisation de Zsh. Bienvenue dans le monde de "Oh My Zsh" ?

Mais ce n'est pas tout. Maintenant, nous allons installer les dépendances pour tirer le meilleur parti de Zsh.

### Étape 5 : Changer le thème par défaut

Oh My Zsh est livré avec un grand nombre de thèmes. Le thème par défaut est robbyrussell, 
mais vous pouvez le changer pour le thème de votre choix. Dans ce scénario, je l'ai changé en agnoster, un thème déjà pré-installé.

Vous devez ensuite sélectionner ce thème dans votre `~/.zshrc`. Pour ouvrir le fichier de configuration 
(.zshrc), exécutez la commande :

```bash
nano ~/.zshrc
```
Ou ouvrez le fichier dans un éditeur de texte avec

```open ~/.zshrc```

Définissez le thème zsh et mettez à jour vos modifications

```source ~/.zhrc```

### Utilisation d'un thème personnalisé

Pour installer un autre thème non préinstallé, clonez le dépôt dans `custom/themesdirectory`. Dans ce scénario, nous allons installer [powerlevel9k](https://github.com/Powerlevel9k/powerlevel9k/wiki/Install-Instructions#option-2-install-for-oh-my-zsh),

```bash 
git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
```

Ensuite, sélectionnez ce thème dans votre `~/.zshrc`

```ZSH_THEME="powerlevel9k/powerlevel9k"```

Mettez à jour vos modifications en exécutant la commande `source ~/.zshrc`

Accédez à `iTerm2 > Préférences > Profils > Couleurs` si vous souhaitez modifier la couleur de fond du terminal.

Le thème sélectionné dans ce scénario nécessite des polices de caractères en ligne. Nous allons donc les installer.

### Étape 6 : Installation des polices

Je vais utiliser [Inconsolata](https://github.com/powerline/fonts/tree/master/Inconsolata). Choisissez votre police préférée parmi ces [polices powerline](https://github.com/powerline/fonts). Ensuite, téléchargez-la et installez-la.

Ou téléchargez la police entière.

```bash
git clone https://github.com/powerline/fonts.git
cd fonts
./install.sh
```

Pour modifier la police, allez dans `iTerm2 > Préférences > Profils > Texte > Modifier la police.`

Vous pouvez maintenant voir que Inconsolata est l'une des polices proposées. Sélectionnez votre police préférée. 
Pour les polices qui prennent en charge les ligatures comme [FiraCode](https://github.com/tonsky/FiraCode), 
cochez l'option "Utiliser les ligatures" pour afficher vos flèches et autres opérateurs de manière élégante comme ( → ).

### Étape 7 : Installation du schéma de couleurs

Changeons le schéma de couleurs pour faire ressortir la beauté de notre terminal. 
Naviguez vers [iTerm2-Color-Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes) et téléchargez le dossier ZIP. Ensuite, extrayez le dossier téléchargé car 
ce dont nous avons besoin se trouve dans le dossier schemes.

Allez dans `iTerm2 > Préférences > Profil > Couleurs > Préréglages de couleur > Importer.`

* Accédez au dossier des schémas et sélectionnez vos schémas de couleurs préférés pour les importer.
* Cliquez sur un modèle de couleurs spécifique pour l'activer. Dans ce scénario, j'ai activé Batman, qui est ma palette de couleurs préférée.

Tada ! ? Nous en avons terminé avec les paramètres de base.

### Étape 8 : Installer les plugins

Oh My ZSH est livré préchargé avec un plugin git. Pour en ajouter d'autres, par exemple, docker, 
auto-suggestion, coloration syntaxique et plus encore :

* Clonez le dépôt Git

```git clone https://github.com/zsh-users/zsh-docker.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-docker```

* Allez dans le répertoire `.oh-my-zsh > custom > plugins` pour voir le répertoire cloné. Pour y accéder, exécutez la commande open `~/.oh-my-zsh`
* Ajoutez le plugin à la section plugin du fichier de configuration `~/.zshrc` comme indiqué ci-dessous.
* Mettez à jour vos modifications en exécutant la commande source `~/.zshrc`

### Étape 9 : ajouter des alias

Les alias sont des raccourcis utilisés pour réduire le temps passé à taper des commandes. Ajoutez des alias aux commandes que vous exécutez dans la section ci-dessous.

_Merci de votre lecture._

Si vous connaissez d'autres moyens d'améliorer la productivité en utilisant ZSH, 
vous pouvez les déposer dans la section des commentaires, je serai heureux de vous entendre.
