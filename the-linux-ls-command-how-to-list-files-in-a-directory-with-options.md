# La commande Linux LS - Comment lister les fichiers d'un répertoire + les options flags

![img cover](https://www.freecodecamp.org/news/content/images/size/w2000/2020/09/article-banner-7.png)

#### Depuis la création d'Unix dans les années 1970, de nombreux systèmes d'exploitation l'ont utilisé comme base. Beaucoup de ces systèmes d'exploitation ont échoué, tandis que d'autres ont réussi.

Linux est l'un des systèmes d'exploitation basés sur Unix les plus populaires. Il est open source et est utilisé dans le monde entier dans de nombreux secteurs.

Une caractéristique étonnante du système d'exploitation Linux est l'interface de ligne de commande (CLI) qui permet aux utilisateurs d'interagir avec leur ordinateur à partir d'un shell. L'interpréteur de commandes Linux est un environnement REPL (Read, Evaluate, Print, Loop) dans lequel les utilisateurs peuvent entrer une commande et l'interpréteur de commandes l'exécute et renvoie un résultat.

La commande ==ls== est l'une des nombreuses commandes Linux qui permettent à un utilisateur de lister des fichiers ou des répertoires à partir du CLI.

Dans cet article, nous allons étudier en profondeur la commande ==ls== et certains des drapeaux les plus importants dont vous aurez besoin au quotidien.

### Conditions préalables

- Un ordinateur avec des répertoires et des fichiers
- Avoir une des distros Linux installée
- Connaissance de base de la navigation dans le CLI
- Un sourire sur votre visage :)

### La commande ls de Linux

La commande ==ls== est utilisée pour répertorier des fichiers ou des répertoires dans Linux et d'autres systèmes d'exploitation basés sur Unix.

Tout comme vous naviguez dans votre explorateur de fichiers ou votre Finder avec une interface graphique, la commande ==ls== vous permet de lister tous les fichiers ou répertoires du répertoire actuel par défaut, et d'interagir avec eux via la ligne de commande.

Lancez votre terminal et tapez ==ls== pour voir cela en action :

![img illustrations](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-20-at-9.40.29-PM.png)

### Comment lister les fichiers d'un répertoire avec des options

La commande ==ls== accepte également certains drapeaux (également connus sous le nom d'options) qui sont des informations supplémentaires qui modifient la façon dont les fichiers ou les répertoires sont listés dans votre terminal.

En d'autres termes, les drapeaux modifient le fonctionnement de la commande ==ls== :

```cmd
 ls [flags] [directory]
 ```
 
 PS : Le mot **contents** utilisé dans tout l'article fait référence aux **fichiers et répertoires** répertoriés, et non au contenu réel des fichiers/répertoires ?
 
### Liste des fichiers du répertoire de travail actuel

Tapez la commande ==ls== pour lister le contenu du répertoire de travail actuel :

![img illustrations](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-20-at-9.40.29-PM.png)

### Lister les fichiers d'un autre répertoire

Tapez la commande ==ls [chemin du répertoire ici]== pour lister le contenu d'un autre répertoire :

![img illustrations](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-20-at-10.32.52-PM.png)

### Lister les fichiers du répertoire racine

Tapez la commande ==ls /== pour lister le contenu du répertoire racine :

![img illustrations](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-20-at-10.46.10-PM.png)

### Lister les fichiers du répertoire parent

Tapez la commande ls ... pour afficher le contenu du répertoire parent situé un niveau au-dessus. Utilisez la commande ==ls ../..== pour afficher le contenu des fichiers situés deux niveaux au-dessus :

![img illustrations](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-20-at-10.48.22-PM.png)

### Lister les fichiers du répertoire personnel de l'utilisateur (/home/user)

Tapez la commande ==ls ~== pour lister le contenu du répertoire personnel de l'utilisateur :

![img illustrations](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-20-at-10.51.19-PM.png)

### Lister uniquement les répertoires

Tapez la commande ==ls -d */== pour lister uniquement les répertoires :

![img illustrations](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-21-at-12.53.05-PM.png)

### Lister les fichiers avec les sous-répertoires

Tapez la commande ==ls *== pour lister le contenu du répertoire avec ses sous-répertoires :

![img illustrations](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-21-at-1.07.54-PM.png)

### Lister les fichiers récursivement

Tapez la commande ==ls -R== pour lister tous les fichiers et répertoires avec leurs sous-répertoires correspondants jusqu'au dernier fichier :

![img illustrations](https://www.freecodecamp.org/news/content/images/2020/09/Screenshot-2020-09-01-at-9.04.56-AM.png)

    Si vous avez beaucoup de fichiers, cette commande peut prendre beaucoup de temps car chaque fichier de chaque répertoire sera imprimé. Vous pouvez à la place spécifier un répertoire dans lequel exécuter cette commande, comme ceci : ls Downloads -R

## Liste des fichiers avec leur taille

Tapez la commande ==ls -s== (le s est en minuscule) pour lister les fichiers ou les répertoires avec leur taille :

![img illustration](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-21-at-12.30.19-PM.png)

### Lister les fichiers au format long

Tapez la commande ==ls -l== pour lister le contenu du répertoire dans un format de tableau avec des colonnes comprenant :

- les permissions du contenu
- nombre de liens vers le contenu
- propriétaire du contenu
- groupe propriétaire du contenu
- taille du contenu en octets
- date/heure de la dernière modification du contenu
- nom du fichier ou du répertoire

![img illustrations](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-20-at-10.52.37-PM.png)

### Lister les fichiers au format long avec des tailles de fichiers lisibles

Tapez la commande ==ls -lh== pour lister les fichiers ou répertoires dans le même format de tableau que ci-dessus, mais avec une autre colonne représentant la taille de chaque fichier/répertoire :

![img illustrations](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-21-at-12.14.33-PM.png)

Notez que les tailles sont indiquées en octets (B), mégaoctets (MB), gigaoctets (GB) ou téraoctets (TB) lorsque la taille du fichier ou du répertoire est supérieure à 1024 octets.

### Lister les fichiers, y compris les fichiers cachés

Tapez la commande ==ls -a== pour lister les fichiers ou répertoires, y compris les fichiers ou répertoires cachés. Sous Linux, tout ce qui commence par un ==.== est considéré comme un fichier caché :

![img cmd](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-21-at-11.12.26-AM.png)

### Lister les fichiers au format long, y compris les fichiers cachés

Tapez la commande ==ls -l -a== ou ==ls -a -l== ou ==ls -la== ou ==ls -al== pour lister les fichiers ou répertoires sous forme de tableau avec des informations supplémentaires, y compris les fichiers ou répertoires cachés :

![img cmd](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-21-at-12.17.01-PM.png)

### Lister les fichiers et les trier par date et heure

Tapez la commande ==ls -t== pour lister les fichiers ou les répertoires et les trier par date de dernière modification dans l'ordre décroissant (du plus grand au plus petit).

Vous pouvez également ajouter l'option ==-r== pour inverser l'ordre de tri comme suit : ==ls -tr== :

![img cmd](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-21-at-12.20.09-PM.png)

### Lister les fichiers et les trier par taille

Tapez la commande ==ls -S== (le **S** est en majuscule) pour lister les fichiers ou les répertoires et les trier par taille dans l'ordre décroissant (du plus grand au plus petit).

Vous pouvez également ajouter l'option ==-r== pour inverser l'ordre de tri, comme suit : ==ls -Sr== :

![img cmd](https://www.freecodecamp.org/news/content/images/2020/08/Screenshot-2020-08-21-at-12.20.38-PM.png)

### Lister les fichiers et imprimer le résultat dans un fichier

Tapez la commande ==ls > output.txt== pour imprimer la sortie de la commande précédente dans un fichier ==output.txt==. Vous pouvez utiliser l'une des options mentionnées précédemment, comme ==-la --== l'essentiel ici est que le résultat sera affiché dans un fichier et non enregistré sur la ligne de commande.

Vous pouvez ensuite utiliser le fichier comme bon vous semble, ou enregistrer le contenu du fichier avec ==cat output.txt== :

![img cmd](https://www.freecodecamp.org/news/content/images/2020/09/Screenshot-2020-09-01-at-9.12.59-AM.png)

# Conclusion

Il existe des tonnes d'autres commandes et combinaisons que vous pouvez explorer pour lister les fichiers et les répertoires en fonction de vos besoins. Une chose à retenir est la possibilité de combiner plusieurs commandes à la fois.

Imaginons que vous vouliez lister un fichier au format long, y compris les fichiers cachés, et le trier par taille de fichier. La commande serait ==ls -alS==, qui est une combinaison de ==ls -l==, ==ls -a== et ==ls -S==.

Si vous oubliez une commande ou si vous n'êtes pas sûr de ce qu'il faut faire, vous pouvez exécuter ==ls --help== ou ==man ls== qui affichera un manuel avec toutes les options possibles pour la commande ==ls== :
![img illustrations](https://www.freecodecamp.org/news/content/images/2020/09/Screenshot-2020-09-01-at-9.57.37-AM.png)

Meric pour la lecture


Auteur:Bolaji Ayodeji

Titre: Software Engineer, Content Creator & Developer Advocate.

