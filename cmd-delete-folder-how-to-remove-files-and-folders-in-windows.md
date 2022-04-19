https://www.freecodecamp.org/news/cmd-delete-folder-how-to-remove-files-and-folders-in-windows/

# cmd Delete Folder - Comment supprimer des fichiers et des dossiers dans Windows

Parfois, il est tout simplement plus rapide de faire les choses avec la ligne de commande.

Dans ce tutoriel rapide, nous verrons comment ouvrir l'Invite de commande, quelques commandes et indicateurs de base, et comment supprimer des fichiers et des dossiers dans l'Invite de commande.

Si vous êtes déjà familiarisé avec les commandes DOS de base, vous pouvez passer directement à la suite.

## Comment ouvrir l'Invite de 

Pour ouvrir l'Invite de commandes, appuyez sur la touche Windows et tapez "cmd".

Cliquez ensuite sur "Exécuter en tant qu'administrateur" :

Après cela, vous verrez une fenêtre d'invite de commande avec des privilèges administratifs :

Si vous ne pouvez pas ouvrir l'Invite de commandes en tant qu'administrateur, ne vous inquiétez pas. Vous pouvez ouvrir une fenêtre normale de l'Invite de commandes en cliquant sur "Ouvrir" au lieu de "Exécuter en tant qu'administrateur".

La seule différence est que vous ne pourrez peut-être pas supprimer certains fichiers protégés, ce qui ne devrait pas être un problème dans la plupart des cas.


## Comment supprimer des fichiers avec la commande `del`

Maintenant que l'Invite de commandes est ouverte, utilisez `cd` pour changer de répertoire et aller là où se trouvent vos fichiers.

J'ai préparé un répertoire sur le bureau appelé Dossier de test. Vous pouvez utiliser la commande `tree /f` pour voir un, eh bien, arbre, de tous les fichiers et dossiers imbriqués :


Pour supprimer un fichier, utilisez la commande suivante : `del "<nom du fichier>"`.

Par exemple, pour supprimer le fichier Test.txt, il suffit d'exécuter `del "Test File.txt"`.

Il se peut qu'une invite vous demande si vous voulez supprimer le fichier. Dans ce cas, tapez "y" et appuyez sur la touche Entrée.

*Remarque* : Les fichiers supprimés à l'aide de la commande `del` ne peuvent pas être récupérés. Faites très attention où et comment vous utilisez cette commande.

Après cela, vous pouvez exécuter `tree /f` pour confirmer que votre fichier a été supprimé :

De plus, astuce bonus : Command Prompt dispose d'une autocomplétion de base. Vous pouvez donc taper `del test`, appuyer sur la touche de tabulation et l'invite de commande le transformera en `del "Test File.txt"`.

## Comment forcer la suppression de fichiers avec la commande `del`

Parfois, les fichiers sont marqués comme étant en lecture seule, et l'erreur suivante s'affiche lorsque vous essayez d'utiliser la commande `del` :

Pour contourner ce problème, utilisez l'option `/f` pour forcer la suppression du fichier. Par exemple, `del /f "Read Only Test File.txt"` :

## Comment supprimer des dossiers avec la commande `rmdir`

Pour supprimer des répertoires/dossiers, vous devez utiliser la commande `rmdir` ou `rd`. Les deux commandes fonctionnent de la même manière, mais nous allons nous en tenir à `rmdir` car elle est un peu plus expressive.

Par ailleurs, dans le reste du tutoriel, j'utiliserai indifféremment les termes répertoire et dossier. "Dossier" est un terme plus récent qui est devenu populaire avec les premières interfaces graphiques de bureau, mais dossier et répertoire signifient fondamentalement la même chose.

Pour supprimer un répertoire, il suffit d'utiliser la commande `rmdir <nom du répertoire>`.

*Remarque* : Tout répertoire supprimé avec la commande `rmdir` ne peut être récupéré. Faites très attention où et comment vous utilisez cette commande.

Dans ce cas, je veux supprimer un répertoire nommé Subfolder, je vais donc utiliser la commande `rmdir Subfolder` :


Mais, si vous vous souvenez de ce qui précède, Subfolder contient un fichier nommé Nested Test File.

Vous pourriez vous rendre dans le répertoire Subfolder et supprimer le fichier, puis revenir avec `cd ..` et exécuter à nouveau la commande `rmdir Subfolder`, mais cela deviendrait fastidieux. Et imaginez s'il y avait un tas d'autres fichiers et répertoires imbriqués !

Comme avec la commande `del`, il existe un drapeau utile que nous pouvons utiliser pour rendre les choses beaucoup plus rapides et plus faciles.

## Comment utiliser le drapeau `/s` avec `rmdir`

Pour supprimer un répertoire, y compris tous les fichiers et sous-répertoires imbriqués, il suffit d'utiliser l'indicateur `/s` :


Il y aura probablement une invite demandant si vous voulez supprimer ce répertoire. Si c'est le cas, tapez simplement "y" et appuyez sur Entrée.

Et le tour est joué ! Voilà tout ce que vous devez savoir pour supprimer des fichiers et des dossiers dans l'invite de commande Windows.

Toutes ces commandes devraient fonctionner dans PowerShell, qui est en fait la version 2.0 de l'Invite de commandes. De plus, PowerShell dispose d'un grand nombre d'alias sympas comme `ls` et `clear` qui devraient vous convenir si vous êtes familier avec la ligne de commande Mac/Linux.

Ces commandes vous ont-elles aidé ? Y a-t-il d'autres commandes que vous trouvez utiles ? Dans tous les cas, faites-moi signe sur Twitter.