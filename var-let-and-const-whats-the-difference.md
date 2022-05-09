# Var, Let, et Const –Quelle est la différence ??
## De nombreuses nouvelles fonctionnalités brillantes sont apparues avec l'ES2015 (ES6). Et maintenant, puisque nous sommes en 2020, on suppose que beaucoup de développeurs JavaScript se sont familiarisés avec ces fonctionnalités et ont commencé à les utiliser. 

Bien que cette hypothèse puisse être partiellement vraie, il est toujours possible que certaines de ces fonctionnalités restent un mystère pour certains développeurs.

L'une des caractéristiques de l'ES6 est l'ajout de ==let== et ==const==, qui peuvent être utilisés pour la déclaration de variables. La question est de savoir ce qui les différencie du bon vieux ==var== que nous utilisions jusqu'à présent. Si vous n'avez toujours pas compris, cet article est pour vous.

Dans cet article, nous discuterons de ==var==, ==let== et ==const== en ce qui concerne leur portée, leur utilisation et leur levage. Au fil de votre lecture, notez les différences entre eux que je vais souligner.

# Var

Avant l'avènement de l'ES6, les déclarations ==var== régnaient en maître. Les variables déclarées avec ==var== posent toutefois des problèmes. C'est pourquoi il était nécessaire que de nouvelles façons de déclarer les variables voient le jour. Avant de discuter de ces problèmes, nous allons d'abord mieux comprendre var.

## Portée de var

La portée signifie essentiellement où ces variables sont disponibles pour être utilisées. Les déclarations ==var== ont une portée globale ou une portée de fonction/locale.
La portée est globale lorsqu'une variable ==var== est déclarée en dehors d'une fonction. Cela signifie que toute variable déclarée avec ==var== en dehors d'un bloc fonctionnel est disponible pour être utilisée dans toute la fenêtre. 

==var== a une portée fonctionnelle lorsqu'elle est déclarée dans une fonction. Cela signifie qu'il est disponible et accessible uniquement dans cette fonction.

Pour mieux comprendre, regardez l'exemple ci-dessous.
```js
 var greeter = "hey hi";

function newFunction() {
    var hello = "hello";
}
```
Ici, ==greeter== a une portée globale car il existe en dehors d'une fonction alors que ==hello== a une portée fonctionnelle. Nous ne pouvons donc pas accéder à la variable hello en dehors d'une fonction. Donc si on fait ça :

```js
    var tester = "hey hi";
    
    function newFunction() {
        var hello = "hello";
    }
    console.log(hello); // error: hello is not defined
```
Nous obtiendrons une erreur qui est due au fait que ==hello== n'est pas disponible en dehors de la fonction.
## Les variables var peuvent être redéclarées et mises à jour.
Cela signifie que nous pouvons le faire dans la même portée et que nous n'obtiendrons pas d'erreur.

```js
    var greeter = "hey hi";
    var greeter = "say Hello instead";
```
et ceci également

```js
    var greeter = "hey hi";
    greeter = "say Hello instead";
```

## Levage de var

Le hissage est un mécanisme JavaScript par lequel les variables et les déclarations de fonctions sont déplacées vers le haut de leur portée avant l'exécution du code. Cela signifie que si nous faisons ceci :

```js
    console.log (greeter);
    var greeter = "say hello"
```

il est interprété comme ceci :

```js
    var greeter;
    console.log(greeter); // greeter is undefined
    greeter = "say hello"
```
Les variables var sont donc hissées au sommet de leur portée et initialisées avec une valeur indéfinie.

# Problème avec var
Il y a une faiblesse qui vient avec ==var==. Je vais utiliser l'exemple ci-dessous pour expliquer :

```js
    var greeter = "hey hi";
    var times = 4;

    if (times > 3) {
        var greeter = "say Hello instead"; 
    }
    
    console.log(greeter) // "say Hello instead"
```

Ainsi, puisque ==times > 3==  renvoie vrai, ==greeter== est redéfini pour =="dire Bonjour à la place"==. Bien que cela ne soit pas un problème si vous voulez sciemment que ==greeter== soit redéfini, cela devient un problème lorsque vous ne réalisez pas que la variable ==greeter== a déjà été définie auparavant.

Si vous avez utilisé ==greeter== dans d'autres parties de votre code, vous pourriez être surpris du résultat que vous pourriez obtenir. Cela causera probablement beaucoup de bogues dans votre code. C'est pourquoi ==let== et ==const== sont nécessaires.
# Let
==let== est désormais privilégié pour la déclaration des variables. Ce n'est pas une surprise car il s'agit d'une amélioration des déclarations de ==var==. Elle résout également le problème de ==var== que nous venons d'aborder. Voyons pourquoi il en est ainsi.
## let a une portée de bloc

Un bloc est un morceau de code délimité par {}. Un bloc vit entre accolades. Tout ce qui se trouve entre accolades est un bloc.

Ainsi, une variable déclarée dans un bloc avec ==let== ne peut être utilisée que dans ce bloc. Laissez-moi vous expliquer cela à l'aide d'un exemple :

```js
    let greeting = "say Hi";
    let times = 4;
    if (times > 3) {
        let hello = "say Hello instead";
        console.log(hello);// "say Hello instead"
    }
    console.log(hello) // hello is not defined
```
Nous voyons que l'utilisation de ==hello== en dehors de son bloc (les accolades où il a été défini) renvoie une erreur. Cela est dû au fait que les variables ==let== ont une portée de bloc.
## let peut être mis à jour mais pas redéclaré.

Tout comme ==var==, une variable déclarée avec ==let== peut être mise à jour dans sa portée. Contrairement à ==var==, une variable ==let== ne peut pas être redéclarée dans son périmètre. Donc, même si cela fonctionne :

```js
    let greeting = "say Hi";
    greeting = "say Hello instead";
```

cela renverra une erreur :

```js
    let greeting = "say Hi";
    let greeting = "say Hello instead"; // error: Identifier 'greeting' has already been declared
```

Toutefois, si la même variable est définie dans différents scopes, il n'y aura pas d'erreur :

```js
    let greeting = "say Hi";
    if (true) {
        let greeting = "say Hello instead";
        console.log(greeting); // "say Hello instead"
    }
    console.log(greeting); // "say Hi"
```
Pourquoi n'y a-t-il pas d'erreur ? C'est parce que les deux instances sont traitées comme des variables différentes puisqu'elles ont des portées différentes.

Ce fait fait de ==let== un meilleur choix que ==var==. Lorsque vous utilisez ==let==, vous n'avez pas à vous soucier de savoir si vous avez déjà utilisé un nom pour une variable auparavant, car une variable n'existe que dans sa portée.

De plus, comme une variable ne peut pas être déclarée plus d'une fois dans une portée, le problème évoqué plus haut, qui se produit avec ==var==, ne se produit pas.

## Levage de  let

Tout comme ==var==, les déclarations ==let== sont hissées au sommet. Contrairement à ==var== qui est initialisé comme ==undefined==, le mot-clé ==let== n'est pas initialisé. Ainsi, si vous essayez d'utiliser une variable ==let== avant sa déclaration, vous obtiendrez une ==erreur de référence==.

# Const

Les variables déclarées avec le ==const== maintiennent des valeurs constantes. Les déclarations ==const== partagent certaines similitudes avec les déclarations ==let==.

## Les déclarations constantes ont une portée de bloc

Comme les déclarations ==let--, les déclarations ==const== ne sont accessibles que dans le bloc où elles ont été déclarées.

## const ne peut être mis à jour ou redéclaré

Cela signifie que la valeur d'une variable déclarée avec ==const== reste la même dans sa portée. Elle ne peut pas être mise à jour ou redéclarée. Donc, si nous déclarons une variable avec ==const==, nous ne pouvons ni faire ceci ni cela :

```js
    const greeting = "say Hi";
    greeting = "say Hello instead";// error: Assignment to constant variable. 
```
ni ceci :

```js
    const greeting = "say Hi";
    const greeting = "say Hello instead";// error: Identifier 'greeting' has already been declared
```
Chaque déclaration const doit donc être initialisée au moment de la déclaration.

Ce comportement est quelque peu différent lorsqu'il s'agit d'objets déclarés avec ==const==. Alors qu'un objet ==const== ne peut pas être mis à jour, les propriétés de cet objet peuvent être mises à jour. Par conséquent, si nous déclarons un objet ==const== comme ceci :

```js
    const greeting = {
        message: "say Hi",
        times: 4
    }
```
alors que nous ne pouvons pas le faire :

```js
    greeting = {
        words: "Hello",
        number: "five"
    } // error:  Assignment to constant variable.
```
nous pouvons le faire :

```js
    greeting.message = "say Hello instead";
```

Cela mettra à jour la valeur de ==greeting.message== sans renvoyer d'erreurs.

## Levage de const

Tout comme ==let==, les déclarations ==const== sont hissées au sommet mais ne sont pas initialisées.
Au cas où vous auriez manqué les différences, les voici :

- Les déclarations ==var== ont une portée globale ou fonctionnelle, tandis que ==let== et ==const== ont une portée de bloc.
- Les variables ==var== peuvent être mises à jour et redéclarées dans leur périmètre ; les variables let peuvent être mises à jour mais pas redéclarées ; les variables const ne peuvent être ni mises à jour ni redéclarées.
 - Elles sont toutes hissées au sommet de leur portée. Mais alors que les variables ==var== sont initialisées avec ==undefined==, les variables ==let== et ==const== ne sont pas initialisées.
- Alors que ==var== et ==let== peuvent être déclarées sans être initialisées, ==const== doit être initialisée lors de la déclaration.
- 
Vous avez des questions ou des ajouts ? N'hésitez pas à me le faire savoir.

Merci de votre lecture :)

## Sarah Chima Atuonwu
