https://www.freecodecamp.org/news/git-revert-commit-how-to-undo-the-last-commit/

# Git Revert Commit - Comment annuler le dernier commit ?

Disons que vous travaillez sur votre code dans Git et que quelque chose ne s'est pas passé comme prévu. Vous avez donc besoin de revenir sur votre dernier commit. Comment faire ? Nous allons le découvrir !

Il y a deux façons possibles d'annuler votre dernière commit. Nous allons les examiner toutes les deux dans cet article.

## la commande `revert`

La commande `revert` créera un commit qui annulera les changements du commit visé. Vous pouvez l'utiliser pour revenir sur le dernier commit comme ceci :

```bash
git revert <commit to revert>
```

Vous pouvez trouver le nom du commit que vous voulez rétablir en utilisant `git log`. Le premier commit qui y est décrit est le dernier commit créé. Vous pouvez alors copier à partir de là le nom alphanumérique et l'utiliser dans la commande `revert`.

![Dans l'image, chaque cercle représente un commit](https://www.freecodecamp.org/news/content/images/2021/08/image-117.png)
Dans l'image, chaque cercle représente un commit


## La commande `reset`

Vous pouvez également utiliser la commande reset pour annuler votre dernier commit. Mais attention - cela changera l'historique des commits, donc vous devriez l'utiliser rarement. Elle déplacera le HEAD, la branche de travail, vers le commit indiqué, et ignorera tout ce qui suit :

```bash
git reset --soft HEAD~1
```

L'option `--soft` signifie que vous ne perdrez pas les changements non validés que vous pourriez avoir.

![Dans l'image, chaque cercle représente un commit.](https://www.freecodecamp.org/news/content/images/2021/08/image-113.png)
Dans l'image, chaque cercle représente un commit.

Si vous voulez revenir au dernier commit et également supprimer toutes les modifications non "staged", vous pouvez utiliser l'option `--hard` :

```bash
git reset --hard HEAD~1
```

Cela annulera le dernier commit, mais aussi toutes les modifications non commises.

![Dans l'image, chaque cercle représente un commit.](https://www.freecodecamp.org/news/content/images/2021/08/image-112.png)
Dans l'image, chaque cercle représente un commit.

## Faut-il utiliser `reset` ou `revert` dans Git ?
Vous ne devriez vraiment utiliser `reset` que si le commit à réinitialiser n'existe que localement. Cette commande modifie l'historique des commits et peut écraser l'historique dont dépendent les membres de l'équipe distante.

`revert` crée plutôt un nouveau commit qui annule les changements, donc si le commit à réinitialiser a déjà été poussé vers un dépôt partagé, il est préférable d'utiliser `revert` car il n'écrase pas l'historique du commit.

## Conclusion
Vous avez appris deux façons d'annuler le dernier commit et aussi quand il est préférable d'utiliser l'une plutôt que l'autre.

Maintenant si vous remarquez que votre dernier commit introduit un bug ou n'aurait pas dû être committé, vous savez comment le corriger !
