https://www.freecodecamp.org/news/how-to-substring-a-string-in-python/

# Comment soustraire une chaîne de caractères en Python ?

Python offre de nombreuses façons de sous-titrer une chaîne de caractères. Cette opération est souvent appelée "découpage en tranches".

Voici la syntaxe :

```py
string[start:end:step]
```

Ici,

`start` : L'indice de départ de la sous-chaîne. Le caractère situé à cet indice est inclus dans la sous-chaîne. Si `start` n'est pas inclus, il est supposé être égal à 0.

`end` : L'indice de fin de la sous-chaîne. Le caractère situé à cet indice n'est pas inclus dans la sous-chaîne. Si `end` n'est pas inclus, ou si la valeur spécifiée dépasse la longueur de la chaîne, elle est supposée être égale à la longueur de la chaîne par défaut.

`step` : Chaque caractère "pas" après le caractère actuel doit être inclus. La valeur par défaut est 1. Si `step` n'est pas inclus, il est supposé être égal à 1.

## Utilisation de base

`string[start:end]` : Récupère tous les caractères du début à la fin - 1

`string[:end]` : Récupère tous les caractères du début à la fin de la chaîne - 1

`string[start:]`: Récupère tous les caractères du début à la fin de la chaîne de caractères.

`string[start:end:step]` : Récupère tous les caractères du début à la fin - 1, sans inclure tous les caractères d'étape.

## Exemples
### 1. Obtenir les 5 premiers caractères d'une chaîne de caractères

```py
string = "freeCodeCamp"
print(string[0:5])
```

Sortie

```bash
> freeC
```

Note : `print(string[:5])` renvoie le même résultat que `print(string[0:5])`


### 2. Obtenez une sous-chaîne de 4 caractères, en commençant par le 3ème caractère de la chaîne.

```py
string = "freeCodeCamp"
print(string[2:6])
```

Sortie

```bash
> eeCo
```

### 3. Obtenez le dernier caractère de la chaîne

```py
string = "freeCodeCamp"
print(string[-1])
```

Sortie

```bash
> p
```

Notez que l'indice de début ou de fin peut être un nombre négatif. Un indice négatif signifie que vous commencez à compter à partir de la fin de la chaîne au lieu du début (de la droite vers la gauche).

L'indice -1 représente le dernier caractère de la chaîne, -2 représente l'avant-dernier caractère et ainsi de suite.

### 4. Obtenir les 5 derniers caractères d'une chaîne de caractères

```py
string = "freeCodeCamp"
print(string[-5:])
```

Sortie

```bash
> eCamp
```

### 5. Obtenez une sous-chaîne qui contient tous les caractères sauf les 4 derniers caractères et le 1er caractère.

```py
string = "freeCodeCamp"
print(string[1:-4])
```

Sortie

```bash
> reeCode
```

### 6. Obtenir un caractère sur deux dans une chaîne de caractères

```py
string = "freeCodeCamp"
print(string[::2])
```

Sortie

```bash
> feCdCm
```
