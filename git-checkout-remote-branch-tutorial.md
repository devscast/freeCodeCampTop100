# Git Checkout Remote Branch Tutorial

### Git est un outil de contrôle de version qui vous permet de maintenir et de visualiser différentes versions de votre application. Lorsqu'une nouvelle mise à jour casse votre application, Git vous permet de revenir à la version précédente.

En plus du versioning, Git vous permet de travailler dans plusieurs environnements en même temps. Dans ce contexte, les environnements multiples sont des branches.

## Pourquoi vous avez besoin de branches

Lorsque vous travaillez avec git, vous disposez d'un environnement (branche) master (également appelé principal). Cette branche particulière contient le code source qui est déployé lorsque votre application est prête pour la production.

Lorsque vous souhaitez mettre à jour votre application, vous pouvez également ajouter des commits (modifications) à cette branche. Pour des changements mineurs, ce n'est peut-être pas un problème, mais pour des changements importants, ce n'est pas idéal. C'est pourquoi d'autres branches existent.

Pour créer et utiliser une nouvelle branche, vous utilisez la commande suivante dans votre terminal dans le répertoire du projet :

``` git
    # create a new branch
    git branch branch-name
    # change environment to the new branch
    git checkout branch-name
```
Sur cette nouvelle branche, vous pouvez créer les nouvelles modifications. Puis, lorsque vous avez terminé, vous pouvez les fusionner avec la branche principale.

Un autre avantage des branches est qu'elles permettent à plusieurs développeurs de travailler simultanément sur le même projet. Si plusieurs développeurs travaillent sur la même branche principale, cela peut être désastreux. Il y a trop de changements entre le code de chaque développeur, et cela se termine généralement par des conflits de fusion.

Avec Git, vous pouvez sauter sur une autre branche (un autre environnement) et y apporter des modifications, tandis que le travail se poursuit dans d'autres branches.

## Que signifie "Git Checkout Remote Branch" ?

Lorsque vous commencez un projet avec Git, vous disposez de deux environnements : la branche master locale (qui existe sur votre ordinateur) et la branche master distante (qui existe sur une plateforme supportant Git comme GitHub).

Vous pouvez pousser des modifications de la branche master locale vers la branche master distante et également tirer des modifications de la branche distante.

Lorsque vous créez une branche localement, elle n'existe que localement jusqu'à ce qu'elle soit poussée vers GitHub où elle devient la branche distante. C'est ce que montre l'exemple suivant :
```git
    # create a new branch
    git branch new-branch
    # change environment to the new branch
    git checkout new-branch
    # create a change
    touch new-file.js
    # commit the change
    git add .
    git commit -m "add new file"
    # push to a new branch
    git push --set-upstream origin new-branch
```

Dans l'exemple ci-dessus, l'origine new-branch devient la branche distante. Comme vous l'avez peut-être remarqué, nous avons créé une nouvelle branche et validé un changement sur celle-ci avant de la pousser vers la nouvelle branche distante.

Mais que se passe-t-il si la branche distante existe déjà, et que nous voulons transférer la branche et toutes ses modifications dans notre environnement local ?

C'est là qu'intervient "Git Checkout Remote Branch".

## Comment créer une branche distante pour Git Checkout

Imaginons qu'il existe une branche distante créée par un autre développeur, et que vous voulez tirer cette branche. Voici comment procéder :

### 1. Récupérer toutes les branches distantes

``` git
    git fetch origin
```
Ceci récupère toutes les branches distantes du dépôt. ==origin== est le nom de la branche distante que vous ciblez. Ainsi, si vous avez un nom de branche ==upstream== distante en amont, vous pouvez appeler ==git fetch upstream==.

### 2. Lister les branches disponibles pour le checkout

Pour voir les branches disponibles pour le checkout, exécutez ce qui suit :
``` git
    git branch -a
```

La sortie de cette commande est la liste des branches disponibles pour le checkout. Pour les branches distantes, vous les trouverez préfixées par ==remotes/origin==.

### 3. Extraire des changements d'une branche distante

Notez que vous ne pouvez pas faire des changements directement sur une branche distante. Par conséquent, vous avez besoin d'une copie de cette branche. Si vous voulez copier la branche distante ==fix-failing-tests==, voici comment procéder :

```git
    git checkout -b fix-failing-tests origin/fix-failing-tests
```

Ce que cela fait est :
* il crée une nouvelle branche appelée ==fix-failing-tests==
*    il ==vérifie== cette branche
*   il tire les changements de ==origin/fix-failing-tests== vers cette branche


Et maintenant vous avez une copie de cette branche distante. Vous pouvez également pousser des commits vers cette branche distante. Par exemple, vous pouvez pousser un nouveau commit comme suit :

```
touch new-file.js
git add .
git commit -m "add new file"
git push
```
Ceci va pousser les changements commis vers ==origin/fix-failing-tests==. Si vous avez remarqué, nous n'avons pas eu à spécifier où nous poussions les changements (comme ==git push origin fix-failing-tests==). C'est parce que git configure automatiquement la branche locale pour suivre la branche distante.

## Conclusion

Les branches de Git facilitent la collaboration pendant le développement d'une application.

Avec les branches, différents développeurs peuvent facilement travailler simultanément sur différentes parties de l'application.

Avec la branche distante de checkout, la collaboration devient encore plus transparente car les développeurs peuvent également copier les branches distantes localement sur leurs systèmes, effectuer des modifications et les pousser vers les branches distantes.

Auteur: Dillion Megida 
skills: Developer Advocate and Content Creator passionate about sharing my knowledge on Tech. I teach JavaScript / ReactJS / NodeJS / React Frameworks / TypeScript / et al


