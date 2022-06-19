https://www.freecodecamp.org/news/subnet-cheat-sheet-24-subnet-mask-30-26-27-29-and-other-ip-address-cidr-network-references/

# Fiche d'information sur les sous-réseaux - Masque de sous-réseau 24, 30, 26, 27, 29, et autres adresses IP réseau de références CIDR

En tant que développeur ou ingénieur réseau, vous pouvez être amené à rechercher occasionnellement les valeurs des masques de sous-réseau et à comprendre leur signification.

Pour vous faciliter la vie, la communauté de freeCodeCamp a créé cette simple fiche de renseignements. Il suffit de faire défiler ou d'utiliser Ctrl/Cmd + f pour trouver la valeur que vous recherchez.

Voici les tableaux, suivis de quelques explications sur leur signification.

| CIDR | MASQUE DE SOUS-RÉSEAU | MASQUE WILDCARD |# D'ADRESSES IP | # D'ADRESSES IP UTILISABLES |
|--|--|--|--|--|
|/32|255.255.255.255|0.0.0.0|1|1|
|/31|255.255.255.254|0.0.0.1|2|2*|
|/30|255.255.255.252|0.0.0.3|4|2|
|/29|255.255.255.248|0.0.0.7|8|6|
|/28|255.255.255.240|0.0.0.15|16|14|
|/27|255.255.255.224|0.0.0.31|32|30|  
|/26|255.255.255.192|0.0.0.63|64|62|  
|/25|255.255.255.128|0.0.0.127|128|126|  
|/24|255.255.255.0|0.0.0.255|256|254|  
|/23|255.255.254.0|0.0.1.255|512|510|  
|/22|255.255.252.0|0.0.3.255|1,024|1,022|  
|/21|255.255.248.0|0.0.7.255|2,048|2,046|  
|/20|255.255.240.0|0.0.15.255|4,096|4,094|  
|/19|255.255.224.0|0.0.31.255|8,192|8,190|  
|/18|255.255.192.0|0.0.63.255|16,384|16,382|  
|/17|255.255.128.0|0.0.127.255|32,768|32,766|  
|/16|255.255.0.0|0.0.255.255|65,536|65,534|  
|/15|255.254.0.0|0.1.255.255|131,072|131,070|  
|/14|255.252.0.0|0.3.255.255|262,144|262,142|  
|/13|255.248.0.0|0.7.255.255|524,288|524,286|  
|/12|255.240.0.0|0.15.255.255|1,048,576|1,048,574|  
|/11|255.224.0.0|0.31.255.255|2,097,152|2,097,150|  
|/10|255.192.0.0|0.63.255.255|4,194,304|4,194,302|  
|/9|255.128.0.0|0.127.255.255|8,388,608|8,388,606|  
|/8|255.0.0.0|0.255.255.255|16,777,216|16,777,214|  
|/7|254.0.0.0|1.255.255.255|33,554,432|33,554,430|  
|/6|252.0.0.0|3.255.255.255|67,108,864|67,108,862|  
|/5|248.0.0.0|7.255.255.255|134,217,728|134,217,726|  
|/4|240.0.0.0|15.255.255.255|268,435,456|268,435,454|  
|/3|224.0.0.0|31.255.255.255|536,870,912|536,870,910|  
|/2|192.0.0.0|63.255.255.255|1,073,741,824|1,073,741,822|  
|/1|128.0.0.0|127.255.255.255|2,147,483,648|2,147,483,646|  
|/0|0.0.0.0|255.255.255.255|4,294,967,296|4,294,967,294|

* /31 est un cas spécial détaillé dans la [RFC 3021](https://tools.ietf.org/html/rfc3021) où les réseaux avec ce type de masque de sous-réseau peuvent attribuer deux adresses IP comme une liaison point à point.

Et voici un tableau des conversions décimales en binaires pour le masque de sous-réseau et les octets de remplacement.

| MASQUE DE SOUS-RÉSEAU | WILDCARD|||
|--|--|--|--|
|0|00000000|255|11111111|  
|128|10000000|127|01111111|  
|192|11000000|63|00111111|  
|224|11100000|31|00011111|  
|240|11110000|15|00001111|  
|248|11111000|7|00000111|  
|252|11111100|3|00000011|  
|254|11111110|1|00000001|  
|255|11111111|0|00000000|

Notez que le caractère générique est simplement l'inverse du masque de sous-réseau.

Si vous êtes novice en matière d'ingénierie des réseaux, vous pouvez vous faire une meilleure idée du [fonctionnement des réseaux informatiques ici.](https://www.freecodecamp.org/news/computer-networks-and-how-to-actually-understand-them-c1401908172d/)

Enfin, cette antisèche et le reste de l'article portent sur les adresses IPv4, et non sur le nouveau protocole IPv6. Si vous souhaitez en savoir plus sur IPv6, consultez l'article sur les réseaux informatiques ci-dessus.

## Comment fonctionnent les blocs d'adresses IP ?

Les adresses IPv4 comme `192.168.0.1` ne sont en fait que des représentations décimales de quatre blocs binaires.

Chaque bloc comporte 8 bits et représente des nombres compris entre 0 et 255. Comme les blocs sont des groupes de 8 bits, chaque bloc est appelé un **octet**. Et comme il y a quatre blocs de 8 bits, chaque adresse IPv4 comporte 32 bits.

Par exemple, voici à quoi ressemble l'adresse IP `172.16.254.1` en binaire :

![](https://www.freecodecamp.org/news/content/images/2021/03/1125px-Ipv4_address.png)
Source : [IPv4](https://en.wikipedia.org/wiki/IPv4)

Pour convertir une adresse IP entre sa forme décimale et sa forme binaire, vous pouvez utiliser ce tableau :

|128|64|32|16|8|4|2|1|
|--|--|--|--|--|--|--|--|
|x|x|x|x|x|x|x|x|

Le graphique ci-dessus représente une octave de 8 bits.

Supposons maintenant que vous vouliez convertir l'adresse IP `168.210.225.206`. Il suffit de diviser l'adresse en quatre blocs (`168`, `210`, `225` et `206`) et de convertir chacun d'eux en binaire à l'aide du tableau ci-dessus.

Rappelez-vous qu'en binaire, 1 est l'équivalent de "on" et 0 de "off". Ainsi, pour convertir le premier bloc, `168`, en binaire, il suffit de commencer au début du tableau et de placer un 1 ou un 0 dans cette cellule jusqu'à ce que vous obteniez une somme de `168`.

|128|64|32|16|8|4|2|1|
|--|--|--|--|--|--|--|--|
|1|0|1|0|1|0|0|0|

128 + 32 + 8 = 168, ce qui, en binaire, donne `10101000`.

Si vous faites de même pour le reste des blocs, vous obtiendrez `10101000.11010010.11100001.11001110`.

## Qu'est-ce que le sous-réseau ?

Si vous regardez le tableau ci-dessus, il peut sembler que le nombre d'adresses IP est pratiquement illimité. Après tout, il existe près de 4,2 milliards d'adresses IPv4 possibles.

Mais si vous pensez à l'ampleur de la croissance d'Internet et au nombre d'appareils connectés de nos jours, vous ne serez pas surpris d'apprendre [qu'il y a déjà une pénurie d'adresses IPv4](https://whatismyipaddress.com/ipv4-shortage).

Cette pénurie ayant été constatée il y a plusieurs années, les développeurs ont trouvé un moyen de diviser une adresse IP en réseaux plus petits appelés sous-réseaux.

Ce processus, appelé "sous-réseau", utilise la section "hôte" de l'adresse IP pour la diviser en petits réseaux ou sous-réseaux.

En général, une adresse IP est composée de bits de réseau et de bits d'hôte :
![](https://www.freecodecamp.org/news/content/images/2021/03/network-and-host-bits.png)

En règle générale, le sous-réseau a deux fonctions : il permet de diviser les réseaux en sous-réseaux et permet aux périphériques de déterminer si un autre périphérique/adresse IP se trouve ou non sur le même réseau local.

Une bonne façon de penser au sous-réseau est d'imaginer votre réseau sans fil à la maison.

Sans sous-réseau, chaque appareil connecté à Internet aurait besoin d'une adresse IP unique.

Mais comme vous avez un routeur sans fil, vous n'avez besoin que d'une seule adresse IP pour votre routeur. Cette adresse IP publique ou externe est généralement gérée automatiquement et est attribuée par votre fournisseur d'accès à Internet (FAI).

Ensuite, chaque appareil connecté à ce routeur possède sa propre adresse IP privée ou interne :

![](https://www.freecodecamp.org/news/content/images/2021/03/home-network-diagram.png)

Source: [What Is My IP Address?](https://www.popularmechanics.com/technology/a32729384/how-to-find-ip-address/)

Maintenant, si votre appareil avec l'adresse IP interne `192.168.1.101` veut communiquer avec un autre appareil, il utilisera l'adresse IP de l'autre appareil et le masque de sous-réseau.

La combinaison des adresses IP et du masque de sous-réseau permet au périphérique `192.168.1.101` de déterminer si l'autre périphérique se trouve sur le même réseau (comme le périphérique `192.168.1.103`) ou sur un réseau complètement différent, quelque part ailleurs en ligne.

Il est intéressant de noter que l'adresse IP externe attribuée à votre routeur par votre fournisseur d'accès fait probablement partie d'un sous-réseau, qui peut inclure de nombreuses autres adresses IP pour des maisons ou des entreprises voisines. Et tout comme les adresses IP internes, elle a également besoin d'un masque de sous-réseau pour fonctionner.

## Fonctionnement des masques de sous-réseau

Les masques de sous-réseau fonctionnent comme une sorte de filtre pour une adresse IP. Avec un masque de sous-réseau, les périphériques peuvent examiner une adresse IP et déterminer quelles parties sont les bits du réseau et quelles parties sont les bits de l'hôte.

Ces éléments permettent ensuite de déterminer la meilleure façon pour ces périphériques de communiquer.

Si vous avez fouillé dans les paramètres réseau de votre routeur ou de votre ordinateur, vous avez probablement vu ce nombre : `255.255.255.0`.

Si c'est le cas, vous avez vu un masque de sous-réseau très courant pour les réseaux domestiques simples.

Comme les adresses IPv4, les masques de sous-réseau sont constitués de 32 bits. Et tout comme la conversion d'une adresse IP en binaire, vous pouvez faire la même chose avec un masque de sous-réseau.

Par exemple, voici notre graphique de tout à l'heure :

|128|64|32|16|8|4|2|1|
|--|--|--|--|--|--|--|--|
|x|x|x|x|x|x|x|x|

Maintenant, nous allons convertir le premier octet, 255 :

|128|64|32|16|8|4|2|1|
|--|--|--|--|--|--|--|--|
|1|1|1|1|1|1|1|1|

Plutôt simple, non ? Donc tout octet qui est `255` est juste `11111111` en binaire. Cela signifie que `255.255.255.0` est en réalité `11111111.11111111.11111111.00000000` en binaire.

Maintenant, regardons ensemble un masque de sous-réseau et une adresse IP et calculons quelles parties de l'adresse IP sont les bits de réseau et les bits d'hôte.

Voici les deux en décimal et en binaire :

TYPE|DÉCIMAL|BINAIRE
|--|--|--|
|Adresse IP|192.168.0.101|11000000.10101000.00000000.0110010|  
|masques de sous-réseau|255.255.255.0|11111111.11111111.11111111.0000000|

Les deux étant disposés de la sorte, il est facile de séparer `192.168.0.101` en bits de réseau et bits d'hôte.

Lorsqu'un bit d'un masque de sous-réseau binaire vaut 1, le même bit d'une adresse IP binaire fait partie du réseau et non de l'hôte.

L'octet `255` étant égal à `11111111` en binaire, tout cet octet de l'adresse IP fait partie du réseau. Ainsi, les trois premiers octets, `192.168.0`, constituent la partie réseau de l'adresse IP, et `101` la partie hôte.

En d'autres termes, si le périphérique `192.168.0.101` veut communiquer avec un autre périphérique, il sait, grâce au masque de sous-réseau, que tout ce qui possède l'adresse IP `192.168.0.xxx` se trouve sur le même réseau local.

Une autre façon d'exprimer cela est avec un ID réseau, qui est juste la partie réseau de l'adresse IP. Ainsi, l'ID réseau de l'adresse `192.168.0.101` avec un masque de sous-réseau de `255.255.255.0` est `192.168.0.0`.

Et il en va de même pour les autres périphériques du réseau local (`192.168.0.102`, 192.168.0.103, etc.).

## Que signifie CIDR et qu'est-ce que la notation CIDR ?

CIDR est l'abréviation de Classless Inter-Domain Routing (routage interdomaine sans classe), et est utilisé dans le routage IPv4 et, plus récemment, IPv6.

![](https://www.freecodecamp.org/news/content/images/2020/05/1920px-IP_Address_Match.svg.png)

Source: [Classless Inter-Domain Routing](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)

La technologie CIDR a été introduite en 1993 afin de ralentir l'utilisation des adresses IPv4, qui étaient rapidement épuisées par l'ancien système d'adressage Classful IP sur lequel Internet a été construit.

Le CIDR englobe deux concepts majeurs.

Le premier est le sous-masquage à longueur variable (VLSM), qui permet aux ingénieurs réseau de créer des sous-réseaux dans les sous-réseaux. Et ces sous-réseaux pouvaient être de tailles différentes, ce qui permettait de réduire le nombre d'adresses IP inutilisées.

Le deuxième grand concept introduit par le CIDR est la notation CIDR.

La notation CIDR est en fait un raccourci pour le masque de sous-réseau et représente le nombre de bits disponibles pour l'adresse IP. Par exemple, le `/24` dans `192.168.0.101/24` est équivalent à l'adresse IP `192.168.0.101` et au masque de sous-réseau `255.255.255.0`.

## Comment calculer la notation CIDR

Pour calculer la notation CIDR d'un masque de sous-réseau donné, il suffit de convertir le masque de sous-réseau en binaire, puis de compter le nombre d'unités ou de chiffres "on". Par exemple :

TYPE|DÉCIMAL|BINAIRE
|--|--|--|
|masques de sous-réseau|255.255.255.0|11111111.11111111.11111111.0000000|

Comme il y a trois octets de uns, il y a 24 bits "on", ce qui signifie que la notation CIDR est `/24`.

Vous pouvez l'écrire de l'une ou l'autre façon, mais je suis sûr que vous conviendrez que `/24` est beaucoup plus facile à écrire que `255.255.255.0`.

Ceci est généralement fait avec une adresse IP, alors regardons le même masque de sous-réseau avec une adresse IP :

TYPE|DÉCIMAL|BINAIRE
|--|--|--|
|Adresse IP|192.168.0.101|11000000.10101000.00000000.01100101|  
|masques de sous-réseau|255.255.255.0|11111111.11111111.11111111.0000000|

Les trois premiers octets du masque de sous-réseau sont tous des bits "on", ce qui signifie que les trois mêmes octets de l'adresse IP sont tous des bits de réseau.

Examinons le quatrième et dernier octet de manière un peu plus détaillée :

TYPE|DÉCIMAL|BINAIRE
|--|--|--|
|Adresse IP|101|01100101|  
|masques de sous-réseau|0|00000000|

Dans ce cas, comme tous les bits de cet octet du masque de sous-réseau sont "éteints", nous pouvons être certains que tous les bits correspondants de cet octet de l'adresse IP font partie de l'hôte.

Lorsque vous écrivez la notation CIDR, vous le faites généralement avec l'ID du réseau. Ainsi, la notation CIDR de l'adresse IP `192.168.0.101` avec un masque de sous-réseau de `255.255.255.0` est `192.168.0.0/24`.

Pour voir d'autres exemples de calcul de la notation CIDR et de l'ID réseau pour une adresse IP et un masque de sous-réseau donnés, regardez cette vidéo :

<iframe width="100%" height="500" src="https://www.youtube.com/embed/XQ3T14SIlV4" frameborder="0" allowfullscreen="true"> </iframe>


## Adressage IP complet

Maintenant que nous avons passé en revue quelques exemples de base de sous-réseau et de CIDR, examinons ce que l'on appelle l'adressage IP par classe.

Avant le développement du sous-réseau, toutes les adresses IP appartenaient à une classe particulière :

![](https://www.freecodecamp.org/news/content/images/2021/03/subnetting.png)

Source: [Subnetting for dummies](https://community.spiceworks.com/networking/articles/2489-subnetting-for-dummies)

Notez qu'il existe des adresses IP de classe D et E, mais nous les étudierons plus en détail un peu plus tard.

Les adresses IP de classe ont permis aux ingénieurs réseau de fournir à différentes organisations une gamme d'adresses IP valides.

Cette approche posait de nombreux problèmes qui ont finalement conduit au sous-réseau. Mais avant de les aborder, examinons de plus près les différentes classes.

## Adresses IP de classe A

Pour les adresses IP de classe A, le premier octet (8 bits / 1 octet) représente l'ID du réseau, et les trois autres octets (24 bits / 3 octets) l'ID de l'hôte.

Les adresses IP de classe A vont de `1.0.0.0` à `127.255.255.255`, avec un masque par défaut de `255.0.0.0` (ou `/8` en CIDR).

Cela signifie que l'adressage de classe A peut avoir un total de 128 (27) réseaux et 16 777 214 (224-2) adresses utilisables par réseau.

Notez également que la plage `127.0.0.0` à `127.255.255.255` de la classe A est réservée à l'adresse de bouclage de l'hôte (voir [RFC5735](https://tools.ietf.org/html/rfc5735)).

## Adresses IP de classe B

Pour les adresses IP de classe B, les deux premiers octets (16 bits / 2 octets) représentent l'ID du réseau et les deux octets restants (16 bits / 2 octets) l'ID de l'hôte.

Les adresses IP de classe B vont de `128.0.0.0` à `191.255.255.255`, avec un masque de sous-réseau par défaut de `255.255.0.0` (ou `/16` en CIDR).

L'adressage de classe B peut avoir 16 384 (214) adresses réseau et 65 534 (216) adresses utilisables par réseau.

## Adresses IP de classe C

Pour les adresses IP de classe C, les trois premiers octets (24 bits / 3 octets) représentent l'ID réseau et le dernier octet (8 bits / 1 octet) est l'ID hôte.

Les adresses IP de classe C vont de `192.0.0.0` à `223.255.255.255`, avec un masque de sous-réseau par défaut de `255.255.255.0` (ou `/24` en CIDR).

La classe C se traduit par 2 097 152 (221) réseaux et 254 (28-2) adresses utilisables par réseau.

Adresses IP de classe D et de classe E
Les deux dernières classes sont la classe D et la classe E.

Les adresses IP de classe D sont réservées aux multidiffusions. Elles occupent la plage allant de `224.0.0.0` à `239.255.255.255`.

Les adresses IP de classe E sont expérimentales, et occupent tout ce qui est supérieur à `240.0.0.0`.

## Le problème des adresses IP par classe

Le principal problème avec les adresses IP par classe est qu'elles n'étaient pas efficaces et qu'elles pouvaient entraîner un grand nombre de pertes d'adresses IP.

Par exemple, imaginez que vous fassiez partie d'une grande organisation à l'époque. Votre entreprise compte 1 000 employés, ce qui signifie qu'elle relèverait de la classe B.

Mais si vous regardez plus haut, vous verrez qu'un réseau de classe B peut prendre en charge jusqu'à 65 534 adresses utilisables. C'est beaucoup plus que ce dont votre entreprise aurait probablement besoin, même si chaque employé avait plusieurs appareils avec une adresse unique.

Et il n'y avait aucun moyen pour votre organisation de se rabattre sur la classe C - il n'y aurait tout simplement pas assez d'adresses IP utilisables.

Ainsi, bien que les adresses IP de classe aient été utilisées à peu près au moment où les adresses IPv4 se sont répandues, il est rapidement devenu évident qu'un meilleur système serait nécessaire pour garantir que nous n'utiliserions pas la totalité des ~4,2 milliards d'adresses utilisables.

Les adresses IP classiques n'ont pas été utilisées depuis qu'elles ont été remplacées par CIDR en 1993, et sont principalement étudiées pour comprendre les débuts de l'architecture d'Internet, et pourquoi le sous-réseau est important.

## J'espère que cet aide-mémoire vous a été utile.

Si vous l'avez trouvée utile, veuillez la partager avec vos amis afin que davantage de personnes puissent en bénéficier.