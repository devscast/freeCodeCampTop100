https://www.freecodecamp.org/news/c-ternary-operator/

# Explication de l'opérateur ternaire en C

Les programmeurs utilisent l'opérateur ternaire pour prendre des décisions à la place des longues instructions conditionnelles if et else.

L'opérateur ternaire prend trois arguments :

1. Le premier est un argument de comparaison
2. Le deuxième est le résultat d'une comparaison vraie
3. Le troisième est le résultat d'une comparaison fausse.

Il est utile de considérer l'opérateur ternaire comme une façon abrégée d'écrire une instruction if-else. Voici un exemple simple de prise de décision utilisant *if* et *else* :

```
int a = 10, b = 20, c;

if (a < b) {
    c = a;
}
else {
    c = b;
}

printf("%d", c);
```

Cet exemple prend plus de 10 lignes, mais ce n'est pas nécessaire. Vous pouvez écrire le programme ci-dessus en seulement 3 lignes de code en utilisant un opérateur ternaire.

### Syntaxe

`condition ? valeur_if_true : valeur_if_false`

L'instruction donne la valeur `value_if_true` si la `condition` est remplie, et `value_if_false` sinon.

Voici l'exemple ci-dessus réécrit pour utiliser l'opérateur ternaire :

```
int a = 10, b = 20, c;

c = (a < b) ? a : b;

printf("%d", c);
```
La sortie de l'exemple ci-dessus devrait être :

```
10
```

`c` est égal à `a`, car la condition `a < b` était vraie.

N'oubliez pas que les arguments `value_if_true` et `value_if_false` doivent être du même type et qu'il doit s'agir d'expressions simples plutôt que de déclarations complètes.

Les opérateurs ternaires peuvent être imbriqués tout comme les instructions if-else. Considérez le code suivant :

```
int a = 1, b = 2, ans;
if (a == 1) {
    if (b == 2) {
        ans = 3;
    } else {
        ans = 5;
    }
} else {
    ans = 0;
}
printf ("%d\n", ans);
```

Voici le code ci-dessus réécrit en utilisant un opérateur ternaire imbriqué :

```
int a = 1, b = 2, ans;
ans = (a == 1 ? (b == 2 ? 3 : 5) : 0);
printf ("%d\n", ans);
```

La sortie des deux ensembles de code ci-dessus devrait être :

```
3
```
