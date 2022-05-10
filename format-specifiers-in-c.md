https://www.freecodecamp.org/news/format-specifiers-in-c/

# Spécification de format en C


Les spécificateurs de format définissent le type de données à imprimer sur la sortie standard. Vous devez utiliser les spécificateurs de format, que vous imprimiez une sortie formatée avec `printf()` ou que vous acceptiez une entrée avec `scanf()`.

Voici quelques-uns des spécificateurs de % que vous pouvez utiliser en ANSI C :



```
SPECIFIER	USED FOR
%c	a single character
%s	a string
%hi	short (signed)
%hu	short (unsigned)
%Lf	long double
%n	prints nothing
%d	a decimal integer (assumes base 10)
%i	a decimal integer (detects the base automatically)
%o	an octal (base 8) integer
%x	a hexadecimal (base 16) integer
%p	an address (or pointer)
%f	a floating point number for floats
%u	int unsigned decimal
%e	a floating point number in scientific notation
%E	a floating point number in scientific notation
%%	the % symbol
```


## Exemples :

### spécificateur de format à caractère unique `%c` :

```c
#include <stdio.h> 

int main() { 
  char first_ch = 'f'; 
  printf("%c\n", first_ch); 
  return 0; 
} 
```

Sortie :

```
f
```

### spécificateur de format de chaîne `%s` :

```c
#include <stdio.h> 

int main() { 
  char str[] = "freeCodeCamp"; 
  printf("%s\n", str); 
  return 0; 
} 
```

Sortie :

```
freeCodeCamp
```

### Entrée de caractères avec le spécificateur de format `%c` :


```c
#include <stdio.h> 

int main() { 
  char user_ch; 
  scanf("%c", &user_ch); // user inputs Y
  printf("%c\n", user_ch); 
  return 0; 
} 
```

Sortie :

```
Y
```

### Entrée de chaîne avec le spécificateur de format `%s` :


```c
#include <stdio.h> 

int main() { 
  char user_str[20]; 
  scanf("%s", user_str); // user inputs fCC
  printf("%s\n", user_str); 
  return 0; 
} 
```

Sortie :

```
fCC
```

### Les spécificateurs de format des nombres entiers décimaux `%d` et `%i` :


```c
#include <stdio.h> 

int main() { 
  int found = 2015, curr = 2020; 
  printf("%d\n", found); 
  printf("%i\n", curr); 
  return 0; 
} 

```

Sortie :

```
2015
2020
```

### Spécification du format des nombres à virgule flottante `%f` et `%e` :


```c
#include <stdio.h>

int main() { 
  float num = 19.99; 
  printf("%f\n", num); 
  printf("%e\n", num); 
  return 0; 
}
```

Sortie :

```
19.990000
1.999000e+01
```


### spécificateur de format d'entier octal `%o` :


```c
#include <stdio.h> 

int main() { 
  int num = 31; 
  printf("%o\n", num); 
  return 0; 
}
```

Sortie :

```
37
```

### spécificateur de format d'entier hexadécimal `%x` :


```c
#include <stdio.h> 

int main() { 
  int c = 28; 
  printf("%x\n", c); 
  return 0; 
} 
```

Sortie :

```
1c
```

