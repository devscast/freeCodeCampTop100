https://www.freecodecamp.org/news/jquery-ajax-post-method/

# La méthode POST de JQuery Ajax

Envoie une requête POST http asynchrone pour charger des données depuis le serveur. Sa forme générale est la suivante :

```js
jQuery.post( url [, data ] [, success ] [, dataType ] )
```

- url : est le seul paramètre obligatoire. Cette chaîne contient l'adresse à laquelle envoyer la requête. Les données renvoyées seront ignorées si aucun autre paramètre n'est spécifié.
- data : Un objet simple ou une chaîne de caractères qui est envoyée au serveur avec la demande.
- success : Une fonction de rappel qui est exécutée si la demande aboutit. Elle prend comme argument les données renvoyées. On lui passe également le statut textuel de la réponse.
- dataType : Le type de données attendu du serveur. La valeur par défaut est Intelligent Guess (xml, json, script, text, html). Si ce paramètre est fourni, alors la callback success doit l'être également.


### Exemples


```js
$.post('http://example.com/form.php', {category:'client', type:'premium'});
```

demande le fichier `form.php` au serveur, en envoyant des données supplémentaires et en ignorant le résultat renvoyé.


```js
$.post('http://example.com/form.php', {category:'client', type:'premium'}, function(response){ 
      alert("success");
      $("#mypar").html(response.amount);
});
```

demande au serveur le fichier `form.php`, envoie des données supplémentaires et traite la réponse retournée (format json). Cet exemple peut être écrit dans ce format :



```js
$.post('http://example.com/form.php', {category:'client', type:'premium'}).done(function(response){
      alert("success");
      $("#mypar").html(response.amount);
});
```

L'exemple suivant affiche un formulaire en utilisant Ajax et place les résultats dans un div.

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>jQuery.post demo</title>
  <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
</head>
<body>
 
<form action="/" id="searchForm">
  <input type="text" name="s" placeholder="Search...">
  <input type="submit" value="Search">
</form>
<!-- the result of the search will be rendered inside this div -->
<div id="result"></div>
 
<script>
// Attach a submit handler to the form
$( "#searchForm" ).submit(function( event ) {
 
  // Stop form from submitting normally
  event.preventDefault();
 
  // Get some values from elements on the page:
  var $form = $( this ),
    term = $form.find( "input[name='s']" ).val(),
    url = $form.attr( "action" );
 
  // Send the data using post
  var posting = $.post( url, { s: term } );
 
  // Put the results in a div
  posting.done(function( data ) {
    var content = $( data ).find( "#content" );
    $( "#result" ).empty().append( content );
  });
});
</script>
 
</body>
</html>
```

L'exemple suivant utilise l'api github pour récupérer la liste des dépôts d'un utilisateur en utilisant jQuery.ajax() et place les résultats dans un div.


```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>jQuery Get demo</title>
  <script src="https://code.jquery.com/jquery-1.10.2.js"></script>
</head>
<body>
 
<form id="userForm">
  <input type="text" name="username" placeholder="Enter gitHub User name">
  <input type="submit" value="Search">
</form>
<!-- the result of the search will be rendered inside this div -->
<div id="result"></div>
 
<script>
// Attach a submit handler to the form
$( "#userForm" ).submit(function( event ) {
 
  // Stop form from submitting normally
  event.preventDefault();
 
  // Get some values from elements on the page:
  var $form = $( this ),
    username = $form.find( "input[name='username']" ).val(),
    url = "https://api.github.com/users/"+username+"/repos";
 
  // Send the data using post
  var posting = $.post( url, { s: term } );
 
  //Ajax Function to send a get request
  $.ajax({
    type: "GET",
    url: url,
    dataType:"jsonp"
    success: function(response){
        //if request if made successfully then the response represent the data

        $( "#result" ).empty().append( response );
    }
  });
  
});
</script>
 
</body>
</html>
```

### jQuery.ajax()

`$.post( url [, data ] [, success ] [, dataType ] )` est une fonction Ajax raccourcie, équivalente à :

```js
$.ajax({
  type: "POST",
  url: url,
  data: data,
  success: success,
  dataType: dataType
});
```


`$.ajax()` offre bien plus d'options, que l'on peut trouver [ici](http://api.jquery.com/jquery.ajax/).

### Plus d'informations :

Pour plus d'informations, veuillez consulter [le site officiel](https://api.jquery.com/jquery.post/)



