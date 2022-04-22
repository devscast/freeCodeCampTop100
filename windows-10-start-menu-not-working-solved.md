https://www.freecodecamp.org/news/windows-10-start-menu-not-working-solved/


# Le menu de démarrage de Windows 10 ne fonctionne pas (résolu)

Windows 10 a parcouru un long chemin depuis son premier lancement en 2015. Chaque mise à jour apporte beaucoup de nouvelles fonctionnalités, et Microsoft a embrassé la communauté open source d'une manière qui était autrefois considérée comme impossible.

Pourtant, comme avec tout système d'exploitation, il y a des bugs. Et l'un des bugs les plus courants auxquels les personnes utilisant Windows 10 ont été confrontées est que le menu Démarrer cesse soudainement de fonctionner.

Parfois, le menu Démarrer ouvert se fige et ne répond pas, et d'autres fois, il ne s'ouvre pas du tout lorsque vous cliquez sur le bouton du menu Démarrer.

Quel que soit le problème spécifique que vous rencontrez avec le menu Démarrer de Windows 10, nous vous présentons dans cet article quelques solutions rapides et moins rapides.

## Comment redémarrer l'Explorateur Windows

L'Explorateur Windows, qui s'appelle désormais l'Explorateur de fichiers, est l'application que vous utilisez pour parcourir votre système de fichiers et ouvrir des programmes et des fichiers. Mais il contrôle également des éléments tels que le menu Démarrer, la barre des tâches et d'autres applications.

Si vous avez un problème avec le menu Démarrer, la première chose que vous pouvez essayer de faire est de redémarrer le processus "Explorateur Windows" dans le Gestionnaire des tâches.

Pour ouvrir le gestionnaire des tâches, appuyez sur les touches *Ctrl + Alt + Suppr*, puis cliquez sur le bouton "Gestionnaire des tâches".

Cliquez sur "Plus de détails" pour obtenir une liste complète des programmes ouverts et des processus d'arrière-plan que vous exécutez :

Faites défiler la liste jusqu'à ce que vous trouviez le processus "Windows Explorer". Faites ensuite un clic droit sur "Windows Explorer" et sélectionnez "Redémarrer" :

Il y aura un bref flash pendant que Windows redémarre l'Explorateur/Finder, ainsi que la barre des tâches et le menu Démarrer.

Après cela, essayez d'ouvrir le menu Démarrer. S'il ne fonctionne toujours pas normalement, essayez l'une des autres solutions ci-dessous.

## Comment réparer les fichiers système Windows corrompus ou manquants ?

Il arrive qu'une mise à jour se passe mal ou que vous supprimiez accidentellement un fichier important en fouillant dans le système de fichiers.

Si le menu Démarrer vous pose toujours problème, ou si d'autres applications centrales de Windows se bloquent, vous pouvez essayer de restaurer les fichiers système Windows manquants ou corrompus.

Pour ce faire, vous devez ouvrir l'invite de commande Windows en tant qu'administrateur et exécuter le programme System File Checker.

Une fois l'invite de commande ouverte en tant qu'administrateur, exécutez la commande  `sfc /scannow` :

System File Checker va commencer à examiner tous vos fichiers système et remplacer tous les fichiers corrompus ou manquants par une copie en cache.

Ce processus peut prendre un certain temps, alors n'hésitez pas à faire autre chose pendant 5 à 10 minutes. Veillez simplement à ne pas fermer la fenêtre pendant que  `sfc` fait son travail.

Une fois que System File Checker a terminé, vous verrez un rapport de tous les fichiers qu'il a remplacés, ou si tout s'est bien passé, vous verrez un message comme celui-ci :

Si System File Checker a remplacé des fichiers système corrompus ou manquants, sauvegardez tout votre travail ouvert et redémarrez votre ordinateur. Lorsque vous vous reconnectez, essayez d'ouvrir le menu Démarrer pour voir si cela a permis de résoudre vos problèmes.

*Remarque* : vous pouvez également utiliser Powershell pour exécuter la commande `sfc /scannow`, mais n'oubliez pas que vous devrez ouvrir un terminal Powershell élevé.

## Comment réinitialiser le menu Démarrer avec les applications Windows 10 par défaut ?

La prochaine chose que vous pouvez essayer est de réinitialiser entièrement le menu Démarrer, ainsi que toutes les applications Windows 10 qui ont été préinstallées ou installées à partir du Microsoft Store.

Pour ce faire, vous devez ouvrir PowerShell en tant qu'administrateur - Command Prompt ne fonctionnera pas pour la commande que vous allez exécuter.

Il existe plusieurs façons d'ouvrir PowerShell, mais l'une des plus rapides est d'utiliser le programme Run.

Utilisez le raccourci *Touche Windows  + R* pour ouvrir le programme Run, entrez "powershell", puis maintenez les touches "Ctrl + Shift" enfoncées et cliquez sur le bouton "OK" :

Cela devrait ouvrir un terminal PowerShell avec des privilèges administratifs.

Dans le terminal PowerShell, exécutez la commande suivante : 

```bash
Get-AppXPackage -AllUsers | Foreach {Add-AppxPackage -DisableDevelopmentMode -Register "$($_.InstallLocation)\AppXManifest.xml"}
```

La commande `Get-AppXPackage` tente de réinstaller toutes les applications Windows par défaut, y compris le menu Démarrer et la barre de recherche.

Elle enregistre également un fichier manifeste pour chaque programme qu'elle réinstalle. Vous n'avez pas à vous soucier des fichiers manifestes, cependant - c'est juste quelque chose dont Windows a besoin pour exécuter chaque programme.

Laissez-lui 5 à 10 minutes et veillez à ne pas fermer la fenêtre PowerShell avant la fin de l'opération.

*Remarque* : il est possible que des erreurs effrayantes s'affichent pendant l'exécution de la commande `Get-AppXPackage`. Ne vous en préoccupez pas - la plupart ne sont que des avertissements expliquant pourquoi un programme ne peut pas être réinstallé :

Lorsque la commande `Get-AppXPackage` est terminée, redémarrez votre ordinateur, connectez-vous et essayez d'ouvrir le menu Démarrer.

## Comment réinitialiser votre installation Windows 10

Si aucune des méthodes ci-dessus n'a permis de réparer le menu Démarrer, la dernière chose que vous pouvez essayer est d'effectuer une réinitialisation d'usine de votre installation Windows 10. Mais gardez à l'esprit qu'il s'agit d'une méthode "presque terre à terre", et qu'elle ne doit être utilisée qu'en dernier recours.

La réinitialisation de votre installation Windows 10 devrait conserver tous vos fichiers personnels intacts (documents, photos, vidéos, etc.), mais désinstallera tous les autres pilotes et programmes que vous avez installés. En gros, cela remet votre ordinateur dans l'état dans lequel il était lorsque vous l'avez allumé pour la première fois.

Avant d'aller plus loin, faites des sauvegardes de tous vos fichiers importants à l'aide d'une clé USB, d'un disque dur/SSD externe et/ou d'un hôte de fichiers en ligne comme Google Drive ou Dropbox.

En fait, faites deux sauvegardes. Vous n'en aurez probablement pas besoin, mais cela ne fait pas de mal.

Lorsque vous avez terminé de sauvegarder tous vos fichiers, ouvrez un terminal PowerShell - utilisez le raccourci clavier *Windows + R*, entrez "powershell", puis cliquez sur le bouton "OK".

Dans le terminal PowerShell, exécutez la commande `systemreset` pour faire apparaître l'assistant de réinitialisation de Windows.

Ensuite, cliquez sur le bouton "Conserver mes fichiers" :

Attendez un moment pendant que l'assistant analyse votre système. Ensuite, vous verrez une liste de tous les programmes qui seront supprimés :

Cliquez sur le bouton "Suivant", et suivez les instructions pour réinitialiser votre installation Windows 10.

Une fois que vous avez terminé de réinitialiser Windows et de créer un nouvel utilisateur, le menu Démarrer devrait fonctionner à nouveau.

## "Cortana, ouvre le menu Démarrer"

Voilà donc toutes les méthodes pour réparer le menu Démarrer de Windows 10, classées de la plus facile à la plus difficile.

L'une de ces méthodes a-t-elle fonctionné pour vous ? Y a-t-il une autre façon d'ouvrir le menu Démarrer que j'ai manquée ?


