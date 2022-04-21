https://www.freecodecamp.org/news/how-to-reverse-a-string-in-javascript-in-3-different-ways-75e4763c68cb/

# Trois façons d'inverser une chaîne en JavaScript

Cet article est basé sur l'algorithme de base de freeCodeCamp Scripting ["Inverser une chaîne"](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-algorithm-scripting/reverse-a-string).

**L'inversion d'une chaîne** est l'une des questions JavaScript les plus fréquemment posées lors des entretiens techniques. Les examinateurs peuvent vous demander d'écrire différentes façons d'inverser une chaîne de caractères, ou ils peuvent vous demander d'inverser une chaîne de caractères sans utiliser les méthodes intégrées, ou ils peuvent même vous demander d'inverser une chaîne de caractères en utilisant la récursion.

Il y a potentiellement des dizaines de façons différentes de le faire, sans compter la fonction intégrée **d'inversion**, car JavaScript n'en a pas.

Vous trouverez ci-dessous mes trois méthodes les plus intéressantes pour résoudre le problème de l'inversion d'une chaîne en JavaScript.

## Défi de l'algorithme

> Inversez la chaîne de caractères fournie.
> Vous devrez peut-être transformer la chaîne en un tableau avant de pouvoir l'inverser.
> Votre résultat doit être une chaîne de caractères.

```javascript
function reverseString(str) {
    return str;
}
reverseString("hello");
```

## Cas de test fournis

- ***reverseString("hello")*** devrait devenir "olleh".
- ***reverseString("Howdy")*** devrait devenir "ydwoH"
- ***reverseString("Salutations de la Terre")*** devrait devenir "htraE morf sgniteerG"

## 1. Inverser une chaîne avec les fonctions intégrées

Pour cette solution, nous allons utiliser trois méthodes : la méthode String.prototype.split(), la méthode Array.prototype.reverse() et la méthode Array.prototype.join().

- La méthode split() divise un objet String en un tableau de chaînes en séparant la chaîne en sous-chaînes.
- La méthode reverse() inverse un tableau en place. Le premier élément du tableau devient le dernier et le dernier devient le premier.
-  La méthode join() joint tous les éléments d'un tableau en une chaîne de caractères.

```javascript
function reverseString(str) {
    // Step 1. Use the split() method to return a new array
    var splitString = str.split(""); // var splitString = "hello".split("");
    // ["h", "e", "l", "l", "o"]
 
    // Step 2. Use the reverse() method to reverse the new created array
    var reverseArray = splitString.reverse(); // var reverseArray = ["h", "e", "l", "l", "o"].reverse();
    // ["o", "l", "l", "e", "h"]
 
    // Step 3. Use the join() method to join all elements of the array into a string
    var joinArray = reverseArray.join(""); // var joinArray = ["o", "l", "l", "e", "h"].join("");
    // "olleh"
    
    //Step 4. Return the reversed string
    return joinArray; // "olleh"
}
 
reverseString("hello");
```

enchaîner les trois méthodes :

```javascript
function reverseString(str) {
    return str.split("").reverse().join("");
}
reverseString("hello");
```

## 2. Inverser une chaîne avec une boucle For décroissante

```javascript
function reverseString(str) {
    // Step 1. Create an empty string that will host the new created string
    var newString = "";
 
    // Step 2. Create the FOR loop
    /* The starting point of the loop will be (str.length - 1) which corresponds to the 
       last character of the string, "o"
       As long as i is greater than or equals 0, the loop will go on
       We decrement i after each iteration */
    for (var i = str.length - 1; i >= 0; i--) { 
        newString += str[i]; // or newString = newString + str[i];
    }
    /* Here hello's length equals 5
        For each iteration: i = str.length - 1 and newString = newString + str[i]
        First iteration:    i = 5 - 1 = 4,         newString = "" + "o" = "o"
        Second iteration:   i = 4 - 1 = 3,         newString = "o" + "l" = "ol"
        Third iteration:    i = 3 - 1 = 2,         newString = "ol" + "l" = "oll"
        Fourth iteration:   i = 2 - 1 = 1,         newString = "oll" + "e" = "olle"
        Fifth iteration:    i = 1 - 1 = 0,         newString = "olle" + "h" = "olleh"
    End of the FOR Loop*/
 
    // Step 3. Return the reversed string
    return newString; // "olleh"
}
 
reverseString('hello');
```
**Sans commentaires** :

```javascript
function reverseString(str) {
    var newString = "";
    for (var i = str.length - 1; i >= 0; i--) {
        newString += str[i];
    }
    return newString;
}
reverseString('hello');
```

## 3. Inverser une chaîne de caractères avec récursion

Pour cette solution, nous allons utiliser deux méthodes : la méthode String.prototype.substr() et la méthode String.prototype.charAt().

- La méthode substr() renvoie les caractères d'une chaîne de caractères à partir de l'emplacement spécifié jusqu'au nombre de caractères spécifié.

```
"hello".substr(1); // "ello"
```

La méthode charAt() renvoie le caractère spécifié dans une chaîne de caractères.

```
"hello".charAt(0); // "h"
```

La profondeur de la récursion est égale à la longueur de la chaîne. Cette solution n'est pas la meilleure et sera vraiment lente si la chaîne est très longue et si la taille de la pile est un problème majeur.

```javascript
function reverseString(str) {
  if (str === "") // This is the terminal case that will end the recursion
    return "";
  
  else
    return reverseString(str.substr(1)) + str.charAt(0);
/* 
First Part of the recursion method
You need to remember that you won’t have just one call, you’ll have several nested calls

Each call: str === "?"        	                  reverseString(str.subst(1))     + str.charAt(0)
1st call – reverseString("Hello")   will return   reverseString("ello")           + "h"
2nd call – reverseString("ello")    will return   reverseString("llo")            + "e"
3rd call – reverseString("llo")     will return   reverseString("lo")             + "l"
4th call – reverseString("lo")      will return   reverseString("o")              + "l"
5th call – reverseString("o")       will return   reverseString("")               + "o"

Second part of the recursion method
The method hits the if condition and the most highly nested call returns immediately

5th call will return reverseString("") + "o" = "o"
4th call will return reverseString("o") + "l" = "o" + "l"
3rd call will return reverseString("lo") + "l" = "o" + "l" + "l"
2nd call will return reverserString("llo") + "e" = "o" + "l" + "l" + "e"
1st call will return reverserString("ello") + "h" = "o" + "l" + "l" + "e" + "h" 
*/
}
reverseString("hello");
```

**Sans commentaires :**

```javascript
function reverseString(str) {
  if (str === "")
    return "";
  else
    return reverseString(str.substr(1)) + str.charAt(0);
}
reverseString("hello");
```

**Opérateur conditionnel (ternaire) :**

```javascript
function reverseString(str) {
  return (str === '') ? '' : reverseString(str.substr(1)) + str.charAt(0);
}
reverseString("hello");
```

**L'inversion d'une chaîne de caractères en JavaScript** est un petit algorithme simple qui peut être demandé lors d'une sélection téléphonique technique ou d'un entretien technique. Vous pouvez résoudre ce problème par la voie la plus courte ou par la voie récursive, voire par des solutions plus complexes.

J'espère que vous avez trouvé cela utile. Ceci fait partie de ma série d'articles "Comment résoudre les algorithmes de FAC" sur les défis algorithmiques du Free Code Camp, où je propose plusieurs solutions et explique étape par étape ce qui se passe sous le capot.


[Trois façons de répéter une chaîne en JavaScript Dans cet article, je vais vous expliquer comment résoudre le défi "Répéter une chaîne de caractères" du freeCodeCamp. Cela implique...](https://www.freecodecamp.org/news/three-ways-to-repeat-a-string-in-javascript-2a9053b93a2d/)


[Deux façons de confirmer la fin d'une chaîne en JavaScript Dans cet article, je vais expliquer comment résoudre le défi "Confirmer la fin" du freeCodeCamp.](https://www.freecodecamp.org/news/two-ways-to-confirm-the-ending-of-a-string-in-javascript-62b4677034ac/)

[Trois façons de factoriser un nombre en JavaScript Cet article est basé sur Free Code Camp Basic Algorithm Scripting "Factorialiser un nombre".](https://www.freecodecamp.org/news/how-to-factorialize-a-number-in-javascript-9263c89a4b38/)

[Deux façons de vérifier les palindromes en JavaScript Cet article est basé sur Free Code Camp Basic Algorithm Scripting "Check for Palindromes".](https://www.freecodecamp.org/news/two-ways-to-check-for-palindromes-in-javascript-64fea8191fd7/)

[Trois façons de trouver le mot le plus long dans une chaîne en JavaScript Cet article est basé sur Free Code Camp Basic Algorithm Scripting "Find the Longest Word in a String".](https://www.freecodecamp.org/news/three-ways-to-find-the-longest-word-in-a-string-in-javascript-a2fb04c9757c/)

[Trois façons de titrer une phrase en JavaScript Cet article est basé sur Free Code Camp Basic Algorithm Scripting "Title Case a Sentence".](https://www.freecodecamp.org/news/three-ways-to-title-case-a-sentence-in-javascript-676a9175eb27/)

Si vous avez votre propre solution ou des suggestions, partagez-les ci-dessous dans les commentaires.

## Resources
- [split() method — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)
- [reverse() method — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)
- [join() method — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
- [String.length — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
- [substr() method — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substr)
- [charAt() method — MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charAt)



