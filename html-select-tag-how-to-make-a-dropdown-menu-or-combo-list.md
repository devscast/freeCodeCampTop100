https://www.freecodecamp.org/news/html-select-tag-how-to-make-a-dropdown-menu-or-combo-list/

# Balise HTML Select - Comment créer un menu déroulant ou une liste déroulante ?

**Vous utilisez la balise HTML select pour créer des menus déroulants afin que les utilisateurs puissent sélectionner la valeur de leur choix. Il s'agit d'une fonction essentielle pour la collecte de données à envoyer à un serveur.**

La balise select est normalement intégrée à un élément de formulaire, les éléments à choisir étant codés dans une autre balise, `<option>`. Il peut également s'agir d'un élément autonome, qui sera toujours associé à un formulaire avec l'un de ses attributs spéciaux, `form`.

Dans ce tutoriel, je vous expliquerai comment créer un menu déroulant avec la balise select afin que vous puissiez commencer à l'utiliser pour collecter des données dans vos projets de codage. Je vous expliquerai également comment styliser la balise select, car elle est réputée pour être difficile à styliser.

## Attributs de la balise select

Avant d'examiner en détail comment créer un menu déroulant avec la balise select, nous devons discuter des attributs de la balise select.

Voici ses attributs :

- name : Vous devez attacher le nom à chaque contrôle de formulaire car il est utilisé pour référencer les données après qu'elles aient été soumises au serveur.
- multiple : Cet attribut permet à l'utilisateur de sélectionner plusieurs options dans le menu déroulant.
- required (obligatoire) : Cet attribut est généralement utilisé pour la validation. Avec cet attribut, le formulaire ne sera pas soumis si l'utilisateur ne sélectionne pas au moins une option dans la liste déroulante.
disabled (désactivé) : Cet attribut empêche l'utilisateur d'interagir avec les options.
- size (taille) : Exprimé en chiffres, l'attribut size est utilisé pour spécifier le nombre d'options qui seront visibles à la fois.
- autofocus : Cet attribut est utilisé sur toutes les entrées de formulaire, select inclus, pour spécifier que l'entrée doit être mise en évidence lorsque la page se charge.


## Comment créer un menu déroulant à l'aide de la balise Select

Pour créer un menu déroulant à l'aide de la balise Select, vous avez d'abord besoin d'un élément de formulaire. En effet, ce dernier contient également un bouton d'envoi (l'élément de formulaire) qui permet de transmettre les données au serveur.


```html
<form action="#">
      <label for="lang">Language</label>
      <select name="languages" id="lang">
        <option value="javascript">JavaScript</option>
        <option value="php">PHP</option>
        <option value="java">Java</option>
        <option value="golang">Golang</option>
        <option value="python">Python</option>
        <option value="c#">C#</option>
        <option value="C++">C++</option>
        <option value="erlang">Erlang</option>
      </select>
      <input type="submit" value="Submit" />
</form>
```

J'ai ajouté quelques feuilles de style CSS simples pour centrer la liste déroulante et le bouton, et donner au corps un fond gris clair :

```css
body {
     display: flex;
     align-items: center;
     justify-content: center;
     margin: 0 auto;
     height: 100vh;
     background-color: #f1f1f1;
}

input{
     display: flex;
     align-items: center;
     justify-content: center;
     margin: 0 auto;
}
```
Pour la rendre plus élaborée et accessible, vous pouvez également attacher la boîte de sélection à un élément d'étiquette, afin qu'elle soit mise en évidence lorsque l'on clique sur le texte de l'étiquette. Vous pouvez le faire avec ce code :

```html
<form action="#">
      <label for="lang">Language</label>
      <select name="languages" id="lang">
        <option value="javascript">JavaScript</option>
        <option value="php">PHP</option>
        <option value="java">Java</option>
        <option value="golang">Golang</option>
        <option value="python">Python</option>
        <option value="c#">C#</option>
        <option value="C++">C++</option>
        <option value="erlang">Erlang</option>
      </select>
      <input type="submit" value="Submit" />
</form>
```

J'ai mis un symbole numérique (#) comme valeur de l'attribut action pour éviter d'obtenir un message 404 lorsque vous cliquez sur le bouton d'envoi.

Mais maintenant nous devons faire un petit changement dans le CSS :


```css
 body {
     display: flex;
     align-items: center;
     justify-content: center;
     margin: 0 auto;
     height: 100vh; 
     background-color: #f1f1f1;
   }

input {
     display: flex;
     align-items: center;
     justify-content: center;
     margin: 0 auto;
   }

label {
     display: flex;
     align-items: center;
     justify-content: center;
     margin: 0 auto;
   }

select {
     margin-bottom: 10px;
     margin-top: 10px;
   }
```

Au final, voici le résultat :

Et ce n'est pas tout. L'un des éléments de la liste déroulante apparaît par défaut et sera sélectionné si l'utilisateur clique sur le bouton d'envoi dès qu'il arrive sur la page.

Mais ce n'est pas une bonne expérience pour l'utilisateur. Vous pouvez vous en débarrasser en codant "sélectionnez une langue" comme premier élément de la liste déroulante.

```html
 <form action="#">
      <label for="lang">Language</label>
      <select name="languages" id="lang">
        <option value="javascript">Select a language</option>
        <option value="javascript">JavaScript</option>
        <option value="php">PHP</option>
        <option value="java">Java</option>
        <option value="golang">Golang</option>
        <option value="python">Python</option>
        <option value="c#">C#</option>
        <option value="C++">C++</option>
        <option value="erlang">Erlang</option>
      </select>
      <input type="submit" value="Submit" />
</form>
```

Lorsque l'utilisateur clique sur la case de sélection pour choisir un élément, la liste déroulante recouvre également le bouton d'envoi - un autre élément qui nuit à la qualité de l'expérience utilisateur.

Vous pouvez changer cela grâce à l'attribut "size", qui affiche un certain nombre d'éléments par défaut et fait défiler les autres éléments de la liste déroulante.

Cela vous permet également de vous débarrasser du premier élément fictif, car certains éléments seront automatiquement visibles par l'utilisateur.

```html
 <form action="#">
      <label for="lang">Language</label>
      <select name="languages" id="lang" size="4">
        <option value="javascript">JavaScript</option>
        <option value="php">PHP</option>
        <option value="java">Java</option>
        <option value="golang">Golang</option>
        <option value="python">Python</option>
        <option value="c#">C#</option>
        <option value="C++">C++</option>
        <option value="erlang">Erlang</option>
      </select>
      <input type="submit" value="Submit" />
</form>
```

Avec l'attribut `multiple`, vous pouvez permettre à l'utilisateur de sélectionner plusieurs éléments dans la liste déroulante.

```html
 <form action="#">
      <label for="lang">Language</label>
      <select name="languages" id="lang" multiple>
        <option value="javascript">JavaScript</option>
        <option value="php">PHP</option>
        <option value="java">Java</option>
        <option value="golang">Golang</option>
        <option value="python">Python</option>
        <option value="c#">C#</option>
        <option value="C++">C++</option>
        <option value="erlang">Erlang</option>
      </select>
      <input type="submit" value="Submit" />
</form>
```

Cela rend 4 éléments visibles par défaut. Pour sélectionner plusieurs éléments, l'utilisateur doit maintenir la touche shift ou ctrl enfoncée, puis sélectionner avec la souris.


That’s not all you can do with the select and `<option>` tags. You can also make a multi-layer select box with the `<optgroup>` element inside a `<select>` tag.

You can convert the already made dropdown to a multi-layer select box like this:


```html
<form action="#">
      <label for="lang">Language</label>
      <select name="languages" id="lang">
        <optgroup label="first-choice">
          <option value="select">Select a language</option>
          <option value="javascript">JavaScript</option>
          <option value="php">PHP</option>
          <option value="java">Java</option>
          <option value="golang">Golang</option>
        </optgroup>
        <optgroup label="second-choice">
          <option value="python">Python</option>
          <option value="c#">C#</option>
          <option value="C++">C++</option>
          <option value="erlang">Erlang</option>
        </optgroup>
      </select>
      <input type="submit" value="Submit" />
</form>
```

## Comment styliser l'élément Select

Le style de l'élément Select est souvent source de confusion et son rendu n'est pas uniforme dans les navigateurs. Mais vous pouvez toujours essayer ce qui suit :


```html
 <form action="#">
      <label for="lang">Language</label>
      <select name="languages" id="lang">
        <option value="select">Select a Language</option>
        <option value="javascript">JavaScript</option>
        <option value="php">PHP</option>
        <option value="java">Java</option>
        <option value="golang">Golang</option>
        <option value="python">Python</option>
        <option value="c#">C#</option>
        <option value="C++">C++</option>
        <option value="erlang">Erlang</option>
      </select>
      <input type="submit" value="Submit" />
</form>
```

```css
select {
    margin-bottom: 10px;
    margin-top: 10px;
    font-family: cursive, sans-serif;
    outline: 0;
    background: #2ecc71;
    color: #fff;
    border: 1px solid crimson;
    padding: 4px;
    border-radius: 9px;
}
```

Dans l'extrait de code CSS ci-dessus, j'ai donné au texte de la boîte de sélection l'apparence suivante :

- une famille de police de type cursive et une couleur blanche,
- un contour de 0 pour supprimer l'horrible contour lorsqu'il est au premier plan,
- un fond verdâtre,
- une bordure de 1 pixel de couleur cramoisie,
- un rayon de bordure de 4 pixels pour obtenir une bordure légèrement arrondie sur tous les côtés,
et un padding de 4 pixels pour espacer un peu les choses.

La boîte de sélection a maintenant une meilleure apparence :


## Conclusion

La balise select est très utile lorsque vous créez des listes déroulantes et des listes combinées en HTML. Il s'agit d'un bouton radio et d'une case à cocher réunis dans un même paquet.

Rappelez-vous qu'avec les boutons radio, vous ne pouvez sélectionner qu'un seul élément dans une liste, alors qu'avec une case à cocher, vous pouvez sélectionner plusieurs éléments. La balise select est plus souple, car vous pouvez la configurer pour qu'elle n'accepte qu'un seul ou plusieurs éléments.

L'un des problèmes de la balise select est qu'elle est très difficile à styliser. Une solution raisonnable consiste à utiliser une bibliothèque CSS qui offre de grandes classes utilitaires pour styliser un formulaire avec l'élément select.

J'espère que ce tutoriel vous a permis de vous familiariser avec la balise select afin que vous puissiez commencer à l'utiliser dans vos projets.

Merci de votre lecture et continuez à coder.