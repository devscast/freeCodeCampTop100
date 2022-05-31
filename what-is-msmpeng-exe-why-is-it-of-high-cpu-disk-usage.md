https://www.freecodecamp.org/news/what-is-msmpeng-exe-why-is-it-of-high-cpu-disk-usage/

# Qu'est-ce que msmpeng.exe ? Pourquoi l'utilisation du disque par le CPU est-elle élevée ?

msmpeng.exe est un élément important de la sécurité de Windows, anciennement connu sous le nom de Windows Defender. Il analyse votre ordinateur à la recherche de diverses menaces allant des logiciels malveillants aux logiciels espions, puis vous propose la ou les solutions appropriées.

Dans cet article, je vais vous expliquer ce qu'est mempeng.exe, la raison pour laquelle il consomme trop de CPU, et 2 façons différentes de l'empêcher d'utiliser trop de CPU.

### Qu'est-ce que msmpeng.exe ?

Msmpeng.exe est l'abréviation de Microsoft Malware Protection Engine. Également connu sous le nom d'exécutable de service Antimalware, il s'agit du programme antivirus intégré aux ordinateurs Windows 10.

Ce programme s'exécute en arrière-plan et analyse votre ordinateur à la recherche de menaces telles que des logiciels nuisibles, des virus, des vers, etc., puis les met en quarantaine ou les supprime.

### Pourquoi msmpeng.exe consomme-t-il beaucoup d'espace disque du CPU ?

msmpeng.exe consomme trop d'espace disque du processeur car il fonctionne activement en arrière-plan et scanne chaque partie de votre ordinateur pendant qu'il le fait. Cela fait bien sûr de msmpeng.exe un programme consommateur de ressources.

En outre, une autre raison pour laquelle msmpeng.exe utilise une quantité élevée de CPU est que le programme analyse son propre dossier (`C:\Program Files\Windows Defender`). Des ressources matérielles faibles ont également été liées au fait que msmpeng.exe consomme trop d'espace disque du processeur.

## Comment empêcher msmpeng.exe d'utiliser trop d'espace disque du processeur ?

Il existe deux moyens principaux d'empêcher l'exécutable du service Antimalware de Windows 10 d'utiliser trop de CPU. Premièrement, vous pouvez empêcher Windows Defender d'analyser son propre dossier et de désactiver la protection en temps réel, et deuxièmement, vous pouvez reprogrammer les analyses de Windows Defender.

### Solution 1 : Empêchez Windows Defender d'analyser son propre dossier

**Étape 1**: Cliquez sur Démarrer ou appuyez sur la touche WIN de votre clavier, puis cliquez sur l'icône de l'engrenage pour ouvrir l'application Paramètres.

**Étape 2** : Cliquez sur "Mise à jour et sécurité" dans la liste.

**Étape 3**: Sélectionnez "Sécurité Windows" et cliquez sur "Protection contre les virus et les menaces".

**Étape 4**: l'application Sécurité Windows s'ouvre. Sous "Paramètres de protection contre les virus et les menaces", cliquez sur le lien "Gérer les paramètres".

**Étape 5** : Faites défiler la liste jusqu'à "Exclusions" et cliquez sur le lien "Ajouter ou supprimer des exclusions".

**Étape 6** : Sur la page suivante, cliquez sur "Ajouter une exclusion", puis sélectionnez "Dossier".

**Étape 7** : Pour éviter les clics multiples, collez `"C:\Program Files\Windows Defender"` dans l'éditeur et cliquez sur "Sélectionner le dossier".

**Étape 8** : Immédiatement après avoir cliqué sur "Sélectionner le dossier", une modale massive apparaîtra - assurez-vous de cliquer sur Oui.

Vous pouvez maintenant voir que le dossier a été ajouté en tant qu'exclusion :

Windows Defender n'analysera plus ce dossier, et le taux d'utilisation du processeur devrait donc diminuer sur votre ordinateur.

### Solution 2 : Désactiver la protection en temps réel et reprogrammer les analyses de Windows Defender

**Étape 1** : Pour désactiver la protection en temps réel et reprogrammer les analyses effectuées par Windows Defender, appuyez sur `WIN` (touche Windows) pour ouvrir la boîte de dialogue Exécuter.

**Étape 2** : Tapez "taskschd.msc" et cliquez sur "OK". L'application Planificateur de tâches s'ouvre alors.

**Étape 3** : Développez l'onglet "Planificateur de tâches", puis sélectionnez "Microsoft", et enfin "Windows".

**Étape 4** : Faites défiler vers le bas et sélectionnez "Windows Defender".
**Étape 5** : Cliquez avec le bouton droit de la souris sur "Windows Defender Scheduled Scan" et sélectionnez "Propriétés".
**Étape 6** : Dans l'onglet Général, décochez la case "Exécuter avec les plus hauts privilèges".
**Étape 7** : Allez dans l'onglet Conditions et assurez-vous que toutes les cases sont décochées.
**Étape 7** : Enfin, allez dans l'onglet Déclencheurs et cliquez sur "Nouveau".
**Étape 8** : enfin, programmez l'heure à laquelle vous souhaitez que Windows Defender lance des analyses, choisissez la fréquence, la date et l'heure, puis cliquez sur "OK". Cliquez à nouveau sur "OK".
**Étape 9** : Redémarrez votre ordinateur. Grâce à cela, msmpeng.exe ne devrait plus consommer trop d'espace disque du processeur.

## Enveloppe

Msmpeng.exe, également connu sous le nom d'exécutable de service Antimalware, est un programme pertinent et efficace qui protège votre ordinateur contre les menaces.

Dans le même temps, il consomme trop d'espace disque du processeur, ce qui peut ralentir votre ordinateur et réduire l'autonomie de la batterie, de sorte que vous pourriez être tenté de le désactiver.

Comme les protections offertes par msmpeng.exe sont utiles, vous devriez chercher des moyens de minimiser ses actions au lieu de le désactiver définitivement, comme cet article vous a montré comment faire.

Si l'utilisation du disque du processeur ne diminue pas, vous pouvez essayer de désactiver Windows Defender de façon permanente - mais assurez-vous d'obtenir un autre programme antivirus pour votre ordinateur si vous faites cela.

Merci d'avoir lu cet article. Pensez à le partager avec vos amis et votre famille si vous le trouvez utile.







