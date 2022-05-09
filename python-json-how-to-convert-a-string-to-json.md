https://www.freecodecamp.org/news/python-json-how-to-convert-a-string-to-json/

# Python JSON - Comment convertir une chaîne en JSON

Dans ce tutoriel, vous apprendrez les bases de JSON - ce qu'il est, où il est le plus couramment utilisé et sa syntaxe.

Vous verrez également comment convertir une chaîne de caractères en JSON en Python.

C'est parti !

## Qu'est-ce que JSON ?

JSON est l'abréviation de JavaScript Object Notation.

Il s'agit d'un format de données utilisé pour le stockage et le transfert d'informations dans les applications Web.

JSON a été inspiré par le langage de programmation JavaScript, mais il n'est pas lié à un seul langage.

La plupart des langages de programmation modernes disposent de bibliothèques permettant d'analyser et de générer des données JSON.

## Où est utilisé JSON ?

JSON est principalement utilisé pour envoyer et recevoir des données entre un serveur et un client, où le client est une page Web ou une application Web.

Il s'agit d'un format beaucoup plus solide à utiliser pendant le cycle demande-réponse que les applications Web utilisent lorsqu'elles se connectent sur un réseau. En comparaison, le XML, compliqué et moins compact, était le format de prédilection il y a quelques années.


## Syntaxe JSON de base

En JSON, les données sont écrites dans des paires clé-valeur, comme ceci :

```json
"first_name": "Katie"
```

Les données sont placées entre guillemets et la paire clé-valeur est séparée par deux points.

Il peut y avoir plus d'une paire clé-valeur et chacune d'elles est séparée par une virgule :

```json
"first_name": "Katie", "last_name": "Rodgers"
```

L'exemple ci-dessus montre un objet, une collection de plusieurs paires clé-valeur.

Les objets sont placés entre accolades :

```json
{
    "first_name": "Katie",  
    "last_name": "Rodgers"
}

```

Vous pouvez également créer des tableaux, une liste ordonnée de valeurs, avec JSON. Dans ce cas, les tableaux sont contenus entre crochets :

```json
[
  { 
      
    "first_name": "Katie",  
    "last_name": "Rodgers"
  },
  
  { 
      
    "first_name": "Naomi",  
    "last_name": "Green"
  },
]

// or:


{
 "employee": [
     { 
    "first_name": "Katie",  
    "last_name": "Rodgers"
  },
  
  { 
    "first_name": "Naomi",  
    "last_name": "Green"
  },
 ]
}

//this created an 'employee' object that has 2 records.
// It defines the first name and last name of an employee
```

## Comment travailler avec des données JSON en Python ?

### Inclure le module JSON pour Python

Pour utiliser JSON avec Python, vous devez d'abord inclure le module JSON en tête de votre fichier Python. Ce module est intégré à Python et fait partie de la bibliothèque standard.

Supposons donc que vous ayez un fichier nommé `demo.py`. En haut du fichier, vous devez ajouter la ligne suivante :

```python
import json
```

### Utilisez la fonction `json.loads()`

Si vous avez des données de type chaîne JSON dans votre programme, par exemple :

```python
#include json library
import json

#json string data
employee_string = '{"first_name": "Michael", "last_name": "Rodgers", "department": "Marketing"}'

#check data type with type() method
print(type(employee_string))

#output
#<class 'str'>
```
vous pouvez le transformer en JSON en Python à l'aide de la fonction `json.loads()`.

La fonction `json.loads()` accepte en entrée une chaîne de caractères valide et la convertit en un dictionnaire Python.

Ce processus est appelé désérialisation, c'est-à-dire la conversion d'une chaîne de caractères en un objet.

```python
#include json library
import json

#json string data
employee_string = '{"first_name": "Michael", "last_name": "Rodgers", "department": "Marketing"}'

#check data type with type() method
print(type(employee_string))

#convert string to  object
json_object = json.loads(employee_string)

#check new data type
print(type(json_object))

#output
#<class 'dict'>
```

Vous pouvez alors accéder à chaque élément individuel, comme vous le feriez en utilisant un dictionnaire Python :

```python
#include json library
import json

#json string data
employee_string = '{"first_name": "Michael", "last_name": "Rodgers", "department": "Marketing"}'

#check data type with type() method
print(type(employee_string))

#convert string to  object
json_object = json.loads(employee_string)

#check new data type
print(type(json_object))

#output
#<class 'dict'>

#access first_name in dictionary
print(json_object["first_name"])

#output
#Michael
```

1. Prenons un autre exemple :

Prenons des données de type chaîne JSON :

```python
import json

#json string
employees_string = '''
{
    "employees": [
       {
           "first_name": "Michael", 
           "last_name": "Rodgers", 
           "department": "Marketing"
        },
       {
           "first_name": "Michelle", 
           "last_name": "Williams", 
           "department": "Engineering"
        }
    ]
}
'''

#check data type using the type() method
print(type(employees_string))

#output
#<class 'str'>
```

2. Utilisez la fonction json.loads() pour convertir une chaîne de caractères en objet :

```python
import json

emoloyees_string = '''
{
    "employees" : [
       {
           "first_name": "Michael", 
           "last_name": "Rodgers", 
           "department": "Marketing"
        },
       {
           "first_name": "Michelle", 
           "last_name": "Williams", 
           "department": "Engineering"
        }
    ]
}
'''

data = json.loads(employees_string)

print(type(data))
#output
#<class 'dict'>
```

3. Accéder aux données :

```python 
import json

employees_string = '''
{
    "employees" : [
       {
           "first_name": "Michael", 
           "last_name": "Rodgers", 
           "department": "Marketing"
           
        },
       {
           "first_name": "Michelle", 
           "last_name": "Williams", 
           "department": "Engineering"
        }
    ]
}
'''

data = json.loads(employees_string)

print(type(data))
#output
#<class 'dict'>

#access first_name
for employee in data["employees"]: 
    print(employee["first_name"])
    
#output
#Michael
#Michelle
```

## Conclusion

Et voilà, vous connaissez maintenant les bases de l'utilisation de JSON en Python.

Si vous voulez en savoir plus sur Python, freeCodeCamp propose une certification Python qui vous emmène des fondamentaux tels que les variables, les boucles et les fonctions à des concepts plus avancés tels que les structures de données. À la fin, vous construirez également 5 projets.

Merci de votre lecture et bon apprentissage !






