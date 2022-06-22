https://www.freecodecamp.org/news/compiled-versus-interpreted-languages/

Langages de programmation interprétés ou compilés : Quelle est la différence ?

![](https://cdn-media-2.freecodecamp.org/w1280/5f9c9e00740569d1a4ca3acf.jpg)

Chaque programme est un ensemble d'instructions, qu'il s'agisse d'additionner deux nombres ou d'envoyer une requête sur Internet. Les compilateurs et les interprètes prennent le code lisible par l'homme et le convertissent en code machine lisible par l'ordinateur.

Dans un langage compilé, la machine cible traduit directement le programme. Dans un langage interprété, le code source n'est pas directement traduit par la machine cible. Au lieu de cela, un programme différent, appelé l'interpréteur, lit et exécute le code.

### D'accord... mais qu'est-ce que cela signifie réellement ?

Imaginez que vous ayez une recette d'houmous à réaliser, mais qu'elle soit écrite en grec ancien. Il y a deux façons pour vous, qui ne parlez pas le grec ancien, de suivre les instructions.

La première est que quelqu'un l'ait déjà traduite en anglais pour vous. Vous (et toute autre personne parlant anglais) pourriez lire la version anglaise de la recette et faire de l'houmous. Considérez cette recette traduite comme la version compilée.

La deuxième possibilité est d'avoir un ami qui connaît le grec ancien. Lorsque vous êtes prêt à faire de l'houmous, votre ami s'assied à côté de vous et traduit la recette en anglais au fur et à mesure, ligne par ligne. Dans ce cas, votre ami est l'interprète de la version interprétée de la recette.

### Langages compilés

Les langages compilés sont convertis directement en code machine que le processeur peut exécuter. Par conséquent, ils ont tendance à être plus rapides et plus efficaces à exécuter que les langages interprétés. Ils permettent également au développeur de mieux contrôler les aspects matériels, comme la gestion de la mémoire et l'utilisation du processeur.

Les langages compilés nécessitent une étape de "construction" - ils doivent d'abord être compilés manuellement. Vous devez "reconstruire" le programme à chaque fois que vous devez apporter une modification. Dans notre exemple d'houmous, la traduction est entièrement écrite avant de vous parvenir. Si l'auteur original décide d'utiliser une autre sorte d'huile d'olive, la recette entière devra être traduite à nouveau et vous être renvoyée.

Les exemples de langages purement compilés sont C, C++, Erlang, Haskell, Rust et Go.

### Langages interprétés

Les interprètes parcourent un programme ligne par ligne et exécutent chaque commande. Ici, si l'auteur décide d'utiliser une autre sorte d'huile d'olive, il peut rayer l'ancienne et ajouter la nouvelle. Votre ami traducteur peut alors vous transmettre ce changement au fur et à mesure.

Les langages interprétés étaient autrefois nettement plus lents que les langages compilés. Mais, avec le développement de la compilation juste-à-temps, cet écart se réduit.

Les exemples de langages interprétés les plus courants sont PHP, Ruby, Python et JavaScript.

### Une petite mise en garde

La plupart des langages de programmation peuvent avoir des implémentations à la fois compilées et interprétées - le langage lui-même n'est pas nécessairement compilé ou interprété. Toutefois, par souci de simplicité, ils sont généralement désignés comme tels.

Python, par exemple, peut être exécuté soit comme un programme compilé, soit comme un langage interprété en mode interactif. D'autre part, la plupart des outils de ligne de commande, des CLI et des shells peuvent théoriquement être classés comme des langages interprétés.

## Avantages et inconvénients

### Avantages des langages compilés

Les programmes qui sont compilés en code machine natif ont tendance à être plus rapides que le code interprété. En effet, le processus de traduction du code au moment de l'exécution augmente les frais généraux et peut entraîner un ralentissement général du programme.

### Inconvénients des langages compilés

Les inconvénients les plus notables sont les suivants :

- Temps supplémentaire nécessaire pour effectuer l'étape de compilation
  complète avant les tests.

- Dépendance du code binaire généré à l'égard de la plate-forme.

### Avantages des langages interprétés

Les langages interprétés ont tendance à être plus flexibles, et offrent souvent des fonctionnalités telles que le typage dynamique et une taille de programme plus petite. En outre, comme les interpréteurs exécutent eux-mêmes le code source du programme, le code lui-même est indépendant de la plate-forme.

### Inconvénients des langages interprétés

L'inconvénient le plus notable est la vitesse d'exécution typique par rapport aux langages compilés.