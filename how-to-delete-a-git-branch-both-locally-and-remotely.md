https://www.freecodecamp.org/news/how-to-delete-a-git-branch-both-locally-and-remotely/

# Comment supprimer une branche Git en local et à distance ?

Dans la plupart des cas, il est simple de supprimer une branche Git. Vous apprendrez dans cet article comment supprimer une branche Git localement et à distance.

## Version abrégée

```bash
// supprimer la branche localement
git branch -d localBranchName

// supprimer la branche à distance
git push origin --delete remoteBranchName
```

## Quand supprimer les branches ?

Il est courant qu'un repo Git comporte différentes branches. Elles constituent un excellent moyen de travailler sur différentes fonctionnalités et corrections tout en isolant le nouveau code de la base de code principale.

Les dépôts ont souvent une branche `main` pour le code principal et les développeurs créent d'autres branches pour travailler sur différentes fonctionnalités.

Une fois le travail terminé sur une fonctionnalité, il est souvent recommandé de supprimer la branche.

## Suppression d'une branche LOCALEMENT

Git ne vous laissera pas supprimer la branche sur laquelle vous êtes actuellement. Vous devez donc vous assurer d'être sur une branche que vous ne voulez PAS supprimer. Par exemple : `git checkout main`

Supprimez une branche avec `git branch -d <branch>.`

Par exemple : `git branch -d fix/authentication`

L'option `-d` ne supprimera la branche que si elle a déjà été poussée et fusionnée avec la branche distante. Utilisez plutôt `-D` si vous voulez forcer la suppression de la branche, même si elle n'a pas encore été poussée ou fusionnée.

La branche est maintenant supprimée localement.

## Suppression d'une branche à DISTANCE
Voici la commande pour supprimer une branche à distance : `git push <remote> --delete <branch>`.

Par exemple : `git push origin --delete fix/authentication`

La branche est maintenant supprimée à distance.

Vous pouvez également utiliser cette commande plus courte pour supprimer une branche à distance : `git push <remote> :<branch>`.

Par exemple : `git push origin :fix/authentication`

Si vous obtenez l'erreur ci-dessous, cela peut signifier que quelqu'un d'autre a déjà supprimé la branche.

```
error: unable to push to unqualified destination: remoteBranchName The destination refspec neither matches an existing ref on the remote nor begins with refs/, and we are unable to guess a prefix based on the source ref. error: failed to push some refs to 'git@repository_name'
```

Essayez de synchroniser votre liste de branches en utilisant :

```
git fetch -p
```

L'option -p signifie "prune" (élaguer). Après la récupération, les branches qui n'existent plus sur le serveur distant seront supprimées.
