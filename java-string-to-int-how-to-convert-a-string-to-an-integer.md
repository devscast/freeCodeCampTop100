https://www.freecodecamp.org/news/java-string-to-int-how-to-convert-a-string-to-an-integer/

# Java String to Int - Comment convertir une chaîne en un nombre entier ?

## Les objets String sont représentés comme une chaîne de caractères.

Si vous avez travaillé avec Java Swing, il possède des composants tels que JTextField et JTextArea que nous utilisons pour obtenir notre entrée à partir de l'interface graphique. Ils prennent notre entrée sous la forme d'une chaîne de caractères.

Si nous voulons créer une calculatrice simple à l'aide de Swing, nous devons trouver comment convertir une chaîne en un nombre entier. Cela nous amène à la question suivante : comment convertir une chaîne de caractères en un nombre entier ?

En Java, nous pouvons utiliser ```Integer.valueOf()``` et ```Integer.parseInt()``` pour convertir une chaîne en un nombre entier.

1. ***Utiliser Integer.parseInt() pour convertir une chaîne en un nombre entier***

Cette méthode renvoie la chaîne sous la forme d'un type primitif int. Si la chaîne ne contient pas un nombre entier valide, elle lèvera une [NumberFormatException](https://docs.oracle.com/javase/7/docs/api/java/lang/NumberFormatException.html).

Ainsi, chaque fois que nous convertissons une chaîne en un nombre entier, nous devons nous occuper de cette exception en plaçant le code à l'intérieur du bloc try-catch.

Prenons un exemple de conversion d'une chaîne de caractères en un nombre entier en utilisant ```Integer.parseInt()```:


```java
    String str = "25";
    try{
        int number = Integer.parseInt(str);
        System.out.println(number); // output = 25
    }
    catch (NumberFormatException ex){
        ex.printStackTrace();
    }
```

Essayons de casser ce code en entrant un nombre entier invalide :

```java
    String str = "25T";
    try{
        int number = Integer.parseInt(str);
        System.out.println(number);
    }
    catch (NumberFormatException ex){
        ex.printStackTrace();
    }
```

Comme vous pouvez le voir dans le code ci-dessus, nous avons essayé de convertir ```25T``` en un nombre entier. Ce n'est pas une entrée valide. Par conséquent, il doit lancer une NumberFormatException.

Voici le résultat du code ci-dessus :

```
java.lang.NumberFormatException: For input string: "25T"
	at java.lang.NumberFormatException.forInputString(NumberFormatException.java:65)
	at java.lang.Integer.parseInt(Integer.java:580)
	at java.lang.Integer.parseInt(Integer.java:615)
	at OOP.StringTest.main(StringTest.java:51)
```

Ensuite, nous allons voir comment convertir une chaîne de caractères en un nombre entier à l'aide de la méthode ```Integer.valueOf()```.

2. ***Utiliser ```Integer.valueOf()``` pour convertir une chaîne de caractères en un nombre entier***

Cette méthode renvoie la chaîne de caractères sous la forme d'un objet entier. Si vous consultez la  [documentation Java](https://docs.oracle.com/javase/7/docs/api/java/lang/Integer.html#valueOf(java.lang.String)), ```Integer.valueOf()``` renvoie un objet entier qui est équivalent à un ```new Integer(Integer.parseInt(s))```.

Nous placerons notre code à l'intérieur du bloc try-catch lorsque nous utiliserons cette méthode. Prenons un exemple d'utilisation de la méthode ```Integer.valueOf()```:

```java
    String str = "25";
    try{
        Integer number = Integer.valueOf(str);
        System.out.println(number); // output = 25
    }
    catch (NumberFormatException ex){
        ex.printStackTrace();
    }
```

Maintenant, essayons de casser le code ci-dessus en entrant un nombre entier invalide :


```java
    String str = "25TA";
    try{
        Integer number = Integer.valueOf(str);
        System.out.println(number); 
    }
    catch (NumberFormatException ex){
        ex.printStackTrace();
    }
```

Comme dans l'exemple précédent, le code ci-dessus lèvera une exception.

Voici la sortie du code ci-dessus :

```
java.lang.NumberFormatException: For input string: "25TA"
	at java.lang.NumberFormatException.forInputString(NumberFormatException.java:65)
	at java.lang.Integer.parseInt(Integer.java:580)
	at java.lang.Integer.valueOf(Integer.java:766)
	at OOP.StringTest.main(StringTest.java:42)
```

Nous pouvons également créer une méthode pour vérifier si la chaîne transmise est numérique ou non avant d'utiliser les méthodes mentionnées ci-dessus.

J'ai créé une méthode simple pour vérifier si la chaîne transmise est numérique ou non.

```java
    public class StringTest {
        public static void main(String[] args) {
            String str = "25";
            String str1 = "25.06";
            System.out.println(isNumeric(str));
            System.out.println(isNumeric(str1));
        }

        private static boolean isNumeric(String str){
            return str != null && str.matches("[0-9.]+");
        }
    }
```

Le résultat est :

```
true
true
```

La méthode ```isNumeric()``` prend une chaîne de caractères comme argument. Elle vérifie d'abord si elle est ```null``` ou non. Ensuite, nous utilisons la méthode ```matches()``` pour vérifier si elle contient des chiffres de 0 à 9 et un point.

Il s'agit d'un moyen simple de vérifier des valeurs numériques. Vous pouvez écrire ou rechercher sur Google des expressions régulières plus avancées pour capturer des valeurs numériques en fonction de votre cas d'utilisation.

La meilleure pratique consiste à vérifier si la chaîne transmise est numérique ou non avant d'essayer de la convertir en nombre entier.

Merci de votre lecture.

Image postée par [🇸🇮 Janko Ferlič](https://unsplash.com/@itfeelslikefilm) sur [Unsplash](https://unsplash.com/collections/139346/soul-care).

Vous pouvez vous connecter avec moi sur [Medium](https://mvthanoshan.medium.com/).