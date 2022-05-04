# Comment supprimer des images et des conteneurs dans Docker

![img cover](https://cdn-media-2.freecodecamp.org/w1280/5f9c9e04740569d1a4ca3ae5.jpg)

## Docker rmi

==docker rmi== supprime les images par leur ID.

Pour supprimer une image, vous devez d'abord lister toutes les images afin d'obtenir leur ID, leur nom et d'autres détails. En exécutant la commande simple ==docker images -a== ou ==docker images==.

Après cela, vous vous assurez de l'image que vous souhaitez supprimer, pour ce faire, exécutez cette commande simple ==docker rmi <votre-image-id>==. Ensuite, vous pouvez confirmer que l'image a été supprimée ou non en listant toutes les images et en vérifiant.

## Supprimer plusieurs images

Il existe un moyen de supprimer plusieurs images à la fois, lorsque vous souhaitez supprimer plusieurs images spécifiques. Donc pour faire cela, obtenez d'abord les ID d'images simplement en listant les images puis exécutez la commande simple suivie.

==docker rmi <votre-image-id> <votre-image-id> ...==

Écrivez les ID des images dans la commande suivie des espaces entre elles.

## Supprimer toutes les images en une seule fois

Pour supprimer toutes les images, il existe une commande simple. ==docker rmi $(docker images -q)==

Ici, dans la commande ci-dessus, il y a deux commandes, la première qui s'exécute dans le ==$()== est une syntaxe shell et renvoie le résultat de ce qui est exécuté dans cette syntaxe. Ainsi, dans ce ==-q- est une option utilisée pour fournir le retour des ID uniques,== $() renvoie les résultats des ID d'image et ensuite ==docker rmi== supprime toutes ces images.

## Pour plus d'informations :
- [Docker CLI docs: rmi](https://docs.docker.com/engine/reference/commandline/rm/)

## Docker rm

==docker rm== supprime les conteneurs par leur nom ou leur ID.

Lorsque des conteneurs Docker sont en cours d'exécution, vous devez d'abord les arrêter avant de les supprimer.

- Arrêtez tous les conteneurs en cours d'exécution : ==docker stop $(docker ps -a -q)==
- Supprimez tous les conteneurs arrêtés : ==docker rm $(docker ps -a -q)==

## Supprimer plusieurs conteneurs

Vous pouvez arrêter et supprimer plusieurs conteneurs en passant aux commandes une liste des conteneurs que vous souhaitez supprimer. La syntaxe shell ==$()== renvoie les résultats de ce qui est exécuté entre les crochets. Vous pouvez donc y créer votre liste de conteneurs à transmettre aux commandes ==stop== et ==rm==.

## Voici une décomposition de docker ps -a -q

- ==docker ps== liste les conteneurs
- L'option ==-a== permet de lister tous les conteneurs, même ceux qui sont arrêtés. Sans cette option, la liste des conteneurs en cours d'exécution est affichée par défaut.
- ==-q== l'option silencieuse pour fournir uniquement les ID numériques des conteneurs, plutôt qu'un tableau complet d'informations sur les conteneurs

## Plus d'informations :
- [Docker CLI docs: rm](https://docs.docker.com/engine/reference/commandline/rm/)

## Plus d'informations sur les images dans Docker :
- [Docker image guide](https://www.freecodecamp.org/news/docker-image-guide-how-to-remove-and-delete-docker-images-stop-containers-and-remove-all-volumes/)
- [Où sont stockées les images Docker ?](https://www.freecodecamp.org/news/where-are-docker-images-stored-docker-container-paths-explained/)

## Plus d'informations sur les conteneurs dans Docker :

- [Comment automatiser le déploiement de conteneurs Docker](https://www.freecodecamp.org/news/automate-docker-container-deployment-via-maven-53a855e26d3e/)
- [Comment corriger les vulnérabilités des conteneurs Docker](https://www.freecodecamp.org/news/how-to-find-and-fix-docker-container-vulnerabilities-in-2020/)

## Plus d'informations sur Docker :

- [Guide de Docker pour les débutants](https://www.freecodecamp.org/news/a-beginners-guide-to-docker-how-to-create-your-first-docker-application-cc03de9b639f/)
- [Cours Docker DevOps (cours vidéo gratuit)](https://www.freecodecamp.org/news/docker-devops-course/)
- [Docker 101 : de la création au déploiement](https://www.freecodecamp.org/news/docker-101-creation-to-deployment/)















