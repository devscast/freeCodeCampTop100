# Modèle HTML5 de base : Utilisez ce modèle HTML de base comme point de départ pour tout projet de développement Web.

![image cover](https://www.freecodecamp.org/news/content/images/size/w2000/2021/07/jackson-so-_t-l5FFH8VA-unsplash.jpg)

### Lorsque vous construisez un nouveau site Web, il est important de disposer d'une bonne base de départ. Dans cet article, je vais vous expliquer ce qu'est un boilerplate HTML 5 et comment créer un modèle de base à utiliser dans vos projets. 

# Qu'est-ce qu'un modèle HTML 5 ?

Selon [Wikipédia](https://en.wikipedia.org/wiki/Boilerplate_code#HTML),

      Le code passe-partout, ou simplement passe-partout, est constitué de sections de code qui sont répétées à plusieurs endroits avec peu ou pas de variation.
      
Un boilerplate en HTML est un modèle que vous ajouterez au début de votre projet. Vous devez ajouter ce modèle à toutes vos pages HTML.
# Exemple de modèle de base HTML 5

Voyons un exemple de base.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>HTML 5 Boilerplate</title>
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
	<script src="index.js"></script>
  </body>
</html>
```
### Qu'est-ce qu'un doctype en HTML ?

La première ligne de votre code HTML doit être la déclaration doctype. Un doctype indique au navigateur dans quelle version de HTML la page est écrite. 

```html
<!DOCTYPE html>
```
Si vous oubliez d'inclure cette ligne de code dans votre fichier, certaines des balises HTML 5 comme ==<article>==, ==< footer>== et ==<header>== risquent de ne pas être prises en charge par le navigateur.
### Qu'est-ce que l'élément racine HTML ?

La balise ==<html>== est l'élément de premier niveau du fichier HTML. Vous emboîterez les balises ==<head>== et ==<body>== à l'intérieur de celle-ci.

```html
<!DOCTYPE html>
<html lang="en">
  <head></head>
  <body></body>
</html>
```

L'attribut ==lang== à l'intérieur de la balise d'ouverture ==<html>== définit la langue de la page. Il est également bon de l'inclure pour des raisons d'accessibilité, car les lecteurs d'écran sauront comment prononcer correctement le texte.

### Que sont les balises head en HTML ?

Les balises ==<head>== contiennent des informations qui sont traitées par les machines. À l'intérieur des balises ==<head>==, vous nicherez des métadonnées qui sont des données qui décrivent le document à la machine.

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>HTML 5 Boilerplate</title>
    <link rel="stylesheet" href="style.css">
</head>
```
### Qu'est-ce que le codage des caractères UTF-8 ?

UTF-8 est le codage de caractères standard que vous devez utiliser dans vos pages Web. Il s'agit généralement de la première balise ==<meta>== affichée dans l'élément ==<head>==.

```html
 <meta charset="UTF-8">
 ```
 Selon le [World Wide Web Consortium](https://www.w3.org/International/questions/qa-choosing-encodings),
 
    Un codage basé sur Unicode tel que UTF-8 peut prendre en charge de nombreuses langues et peut accueillir des pages et des formulaires dans n'importe quel mélange de ces langues. Son utilisation élimine également le besoin d'une logique côté serveur pour déterminer individuellement le codage des caractères pour chaque page servie ou chaque soumission de formulaire entrant.

### Qu'est-ce que la métabalise viewport en HTML ?

Cette balise permet de rendre la largeur de la page en fonction de la taille de l'écran de l'appareil. Si votre appareil mobile a une largeur de 600 pixels, la fenêtre du navigateur aura également une largeur de 600 pixels.

La balise initial-scale contrôle le niveau de zoom. La valeur 1 pour l'échelle initiale empêche le zoom par défaut des navigateurs. 

```html
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### Que signifie X-UA-Compatible ?

Cette balise <meta> spécifie le mode de document pour Internet Explorer. IE=edge est le mode le mieux supporté.

```html
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
```

### Que sont les balises de titre HTML ?

La balise <title> est le titre de la page Web. Ce texte s'affiche dans la barre de titre du navigateur.
```html
    <title>HTML 5 Boilerplate</title>
```
![image cover](https://www.freecodecamp.org/news/content/images/2021/07/Screen-Shot-2021-07-30-at-4.15.25-AM.png)

### Feuille de style CSS

Ce code permettra de lier votre CSS personnalisé à la page HTML. rel="stylesheet" définit la relation entre le fichier HTML et la feuille de style externe.  

```html
    <link rel="stylesheet" href="style.css">
```

### Balises de script dans le HTML

Les balises de script externes sont placées juste avant la balise de fin de corps. C'est là que vous pouvez lier votre code JavaScript externe.

```html
	<script src="index.js"></script>
```

# Conclusion

Vous devriez ajouter un boilerplate HTML 5 à chacune de vos pages HTML. Ce code de démarrage contient des informations importantes comme le doctype, les métadonnées, les feuilles de style externes et les balises de script. 


Auteur: Jessica Wilkins
Titre: I am a musician and a programmer. 
