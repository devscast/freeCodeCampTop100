# Comment annuler des modifications dans Git

![img cover](https://cdn-media-1.freecodecamp.org/images/0*6JjR02sGP4FgM6zj.png)

#### Vous savez peut-être déjà que Git est comme un système de points de sauvegarde. Ce que vous apprenez généralement avec Git au départ, c'est d'apprendre à sauvegarder vos modifications et à les commiter sur un dépôt distant. Mais comment annuler une modification, et revenir à un état antérieur ?

C'est ce que nous allons aborder dans cet article.

J'ai couvert le contenu de cet article dans une vidéo si vous aimez apprendre en regardant plutôt qu'en lisant.

### Local et distant

Il est plus compliqué d'annuler quelque chose qui se trouve déjà sur le site distant. C'est pourquoi il est préférable de garder les choses en local jusqu'à ce qu'elles soient confirmées.

### Quatre scénarios courants

Nous couvrirons les quatre scénarios suivants, qui sont les plus courants

1. Abandon des modifications locales
2. Modification de la livraison précédente
3. Revenir à un commit précédent
4.  Annulation d'un commit qui a été poussé vers le serveur distant.

Note : Dans les captures d'écran ci-dessous, j'ai utilisé le client [Git de Fork pour Mac OS](https://git-fork.com/). Vous pouvez faire la même chose avec d'autres clients Git similaires.
## Scénario 1 : Abandon des modifications locales

Le premier scénario est celui où vous avez créé quelques changements. Ils n'ont pas encore été validés. Et vous voulez supprimer ces changements.

Disons que nous voulons créer une nouvelle fonctionnalité. Nous allons ajouter du HTML et du CSS dans le projet :

```css
<!--In index.html-->
<div class="feature"></div>
```

```css
/* In CSS file */
.feature {
  font-size: 2em; 
  /* Other styles */
}
```
Pour annuler ces modifications :

1. Allez dans la zone de transit
2. Sélectionnez les fichiers pour lesquels vous souhaitez supprimer les modifications.
3. Faites un clic droit sur les fichiers
4. Sélectionnez "Annuler les modifications".

![image img](https://cdn-media-1.freecodecamp.org/images/0*6JjR02sGP4FgM6zj.png)

### Scénario 2 : Modifier le commit précédent

Lorsque vous avez créé un commit et que vous avez manqué quelques changements, vous voulez ajouter ces changements dans le message du commit précédent.

1. Allez dans la zone de mise en scène
2. Mettez en scène les fichiers à commettre
3. Cliquez sur la case à cocher modifier
4. Editez votre message de commit
5. Commit
![image img](https://cdn-media-1.freecodecamp.org/images/0*1wkCc2i9X8JWsBz4.png)

### Scénario 3 : Retour à un commit précédent

Vous avez déjà quelques commits dans votre dépôt local. Vous décidez que vous ne voulez plus de ces commits et vous voulez "charger" vos fichiers à partir d'un état antérieur.

1. Allez dans l'historique Git
2. Cliquez avec le bouton droit de la souris sur le commit auquel vous voulez revenir.
3. Sélectionnez reset ==branch== to here
![image img](https://cdn-media-1.freecodecamp.org/images/0*IwWQ9XZNRmCaVvb8.png)

    Note : Vous ne pouvez réinitialiser qu'un commit qui n'a pas été poussé sur le serveur distant.

### Scénario 4 : Rétablir un commit qui a été poussé dans la branche distante

Si vous avez un commit qui a été poussé dans la branche distante, vous devez le rétablir.

    Revenir en arrière signifie annuler les changements en créant un nouveau commit. Si vous avez ajouté une ligne, ce commit revert va supprimer cette ligne. Si vous avez supprimé une ligne, ce commit revert ajoutera la ligne en question.

Pour revenir en arrière, vous pouvez :

1. Aller dans l'historique Git
2. Faire un clic droit sur le commit que vous voulez inverser
3. Sélectionner "Revert commit
4. S'assurer que la case "commit the changes" est cochée.
5. Cliquez sur revenir en arrière

![image img](https://cdn-media-1.freecodecamp.org/images/0*29rgArX4rXn3aH6x.png)

![image img](https://cdn-media-1.freecodecamp.org/images/0*fUD5rUESrzaMnbXu.png)

### Autres scénarios

GitHub propose un article utile qui vous montre comment annuler presque tout avec Git. Il vous sera utile si vous êtes confronté à d'autres scénarios. Lisez-le [ici](https://blog.github.com/2015-06-08-how-to-undo-almost-anything-with-git/).

Merci de votre lecture. Cet article vous a-t-il aidé d'une quelconque manière ? Si oui, [j'espère que vous envisagerez de le partager](http://twitter.com/share?text=Undoing%20changes%20in%20Git%20by%20@zellwk%20?%20&url=https://zellwk.com/blog/git-undo/&hashtags=). Vous pourriez aider quelqu'un. Merci !

Cet article a été initialement publié sur [mon blog](https://zellwk.com/blog/git-undo).
Inscrivez-vous à ma [newsletter](https://zellwk.com/) si vous voulez plus d'articles pour vous aider à devenir un meilleur développeur frontend.


Auteur:Zell Liew 
Bio: Read [more posts](https://www.freecodecamp.org/news/author/zellwk/) by this author.

