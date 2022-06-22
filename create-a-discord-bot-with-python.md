https://www.freecodecamp.org/news/create-a-discord-bot-with-python/

# Tutoriel Python Discord Bot - Coder un Discord Bot et l'héberger gratuitement

Ce tutoriel vous montre comment créer votre propre robot Discord entièrement dans le nuage.

Vous n'avez pas besoin d'installer quoi que ce soit sur votre ordinateur et vous n'avez pas besoin de payer quoi que ce soit pour héberger votre robot.

Nous allons utiliser un certain nombre d'outils, notamment l'API Discord, des bibliothèques Python et une plate-forme de cloud computing appelée Repl.it.

Il existe également une version vidéo de ce tutoriel écrit. La vidéo est intégrée ci-dessous et la version écrite se trouve après la vidéo

## Comment créer un compte Discord Bot

Pour pouvoir travailler avec la bibliothèque Python et l'API Discord, nous devons d'abord créer un compte Discord Bot.

Voici les étapes de la création d'un compte Discord Bot.

1. Assurez-vous que vous êtes connecté au site Web de Discord.

2. Naviguez jusqu'à la page d'application.

3. Cliquez sur le bouton "Nouvelle candidature".

4. Donnez un nom à l'application et cliquez sur "Créer".

5. Allez dans l'onglet "Bot" et cliquez sur "Add Bot". Vous devrez confirmer en cliquant sur "Oui, faites-le !".

Conservez les paramètres par défaut pour le bot public (coché) et l'octroi de code OAuth2 obligatoire (décoché).

Votre robot a été créé. L'étape suivante consiste à copier le jeton.
Ce jeton est le mot de passe de votre robot, ne le partagez avec personne. Il pourrait permettre à quelqu'un de se connecter à votre bot et de faire toutes sortes de mauvaises choses.

Vous pouvez régénérer le jeton s'il est accidentellement partagé.

## Comment inviter votre robot à rejoindre un serveur ?

Vous devez maintenant faire en sorte que votre utilisateur bot rejoigne un serveur. Pour ce faire, vous devez créer une URL d'invitation pour lui.

Allez dans l'onglet "OAuth2". Sélectionnez ensuite "bot" dans la section "scopes".


Choisissez maintenant les autorisations que vous souhaitez pour le bot. Notre bot va principalement utiliser des messages texte, nous n'avons donc pas besoin de beaucoup d'autorisations. Vous pouvez en avoir besoin de plus en fonction de ce que vous voulez que votre bot fasse. Faites attention à l'autorisation "Administrateur".

Après avoir sélectionné les autorisations appropriées, cliquez sur le bouton "Copier" au-dessus des autorisations. Cela permet de copier une URL qui peut être utilisée pour ajouter le bot à un serveur.

Collez l'URL dans votre navigateur, choisissez un serveur auquel inviter le bot, puis cliquez sur "Autoriser".

Pour ajouter le bot, votre compte doit disposer des droits "Manage Server".

Maintenant que vous avez créé l'utilisateur du robot, nous allons commencer à écrire le code Python du robot.
## Comment coder un robot Discord de base avec la bibliothèque discord.py ?

Nous allons utiliser la bibliothèque Python discord.py pour écrire le code du robot. discord.py est un wrapper API pour Discord qui facilite la création d'un robot Discord en Python.
### Comment créer un Repl et installer discord.py

Vous pouvez développer le robot sur votre ordinateur local avec n'importe quel éditeur de code. Cependant, dans ce tutoriel, nous utiliserons Repl.it pour faciliter le travail de chacun. Repl.it est un IDE en ligne que vous pouvez utiliser dans votre navigateur Web.

Commencez par vous rendre sur Repl.it. Créez un nouveau Repl et choisissez "Python" comme langage.

Pour utiliser la bibliothèque `discord.py`, écrivez simplement `import discord` en haut du fichier `main.py`. Repl.it installera automatiquement cette dépendance lorsque vous appuierez sur le bouton "run".

Si vous préférez coder le bot localement, vous pouvez utiliser cette commande sur MacOS pour installer `discord.py` :


```py
python3 -m pip install -U discord.py
```

Vous devrez peut-être utiliser `pip3` au lieu de `pip`.

Si vous utilisez Windows, alors vous devriez utiliser la ligne suivante à la place :


```py
py -3 -m pip install -U discord.py
```

### Comment configurer les événements Discord pour votre robot ?

discord.py tourne autour du concept d'événements. Un événement est quelque chose que vous écoutez et auquel vous répondez. Par exemple, lorsqu'un message arrive, vous recevez un événement à ce sujet auquel vous pouvez répondre.

Créons un robot qui répond à un message spécifique. Ce code de robot simple, ainsi que l'explication du code, sont tirés de [la documentation discord.py](https://discordpy.readthedocs.io/en/latest/quickstart.html#a-minimal-bot). Nous ajouterons plus tard d'autres fonctionnalités au robot.

Ajoutez ce code au fichier main.py. (Vous pouvez nommer le fichier autrement si vous le souhaitez, mais pas discord.py.) Je vous expliquerai bientôt ce que fait ce code.


```py
import discord
import os

client = discord.Client()

@client.event
async def on_ready():
    print('We have logged in as {0.user}'.format(client))

@client.event
async def on_message(message):
    if message.author == client.user:
        return

    if message.content.startswith('$hello'):
        await message.channel.send('Hello!')

client.run(os.getenv('TOKEN'))
```

Lorsque vous avez créé votre utilisateur de robot sur Discord, vous avez copié un jeton. Nous allons maintenant créer un fichier `.env` pour stocker le jeton. Si vous exécutez votre code localement, vous n'avez pas besoin du fichier `.env`. Remplacez simplement `os.getenv('TOKEN')` par le jeton.

Les fichiers `.env` sont utilisés pour déclarer les variables d'environnement. Sur Repl.it, la plupart des fichiers que vous créez sont visibles par tous, mais les fichiers `.env` ne sont visibles que par vous.  Les autres personnes qui consultent un Repl public ne seront pas en mesure de voir le contenu du fichier `.env`.

Donc, si vous développez sur Repl.it, n'incluez que des informations privées comme des jetons ou des clés dans un fichier `.env`.

Cliquez sur le bouton "Add file" et créez un fichier nommé `.env`.

Dans le fichier, ajoutez la ligne suivante, en incluant le jeton que vous avez copié précédemment :

```
TOKEN=[paste token here]
```


Voyons maintenant ce que fait chaque ligne de code dans le code de votre robot Discord.

1. La première ligne importe la bibliothèque discord.py.
2. La deuxième ligne importe la bibliothèque os, mais elle est uniquement utilisée pour récupérer la variable TOKEN du fichier .env. Si vous n'utilisez pas de fichier .env, vous n'avez pas besoin de cette ligne.
3. Ensuite, nous créons une instance d'un client. Il s'agit de la connexion à Discord.
4. Le décorateur @client.event() est utilisé pour enregistrer un événement. Comme il s'agit d'une bibliothèque asynchrone, les choses se font avec des callbacks. Un callback est une fonction qui est appelée lorsque quelque chose d'autre se produit. Dans ce code, l'événement on_ready() est appelé lorsque le robot est prêt à être utilisé. Ensuite, lorsque le robot reçoit un message, l'événement on_message() est appelé.
5. L'événement on_message() se déclenche à chaque fois qu'un message est reçu, mais nous ne voulons pas qu'il fasse quoi que ce soit si le message provient de nous-mêmes. Donc, si l'auteur du message est le même que l'utilisateur du client, le code renvoie simplement le message.
6. Ensuite, nous vérifions si le Message.content commence par '$hello'. Si c'est le cas, le robot répond par 'Hello!' au canal dans lequel il a été utilisé.
7. Maintenant que le robot est configuré, la dernière ligne lance le robot avec le jeton de connexion. Il récupère le jeton dans le fichier .env.

Nous avons le code du robot, il ne nous reste plus qu'à l'exécuter.
### Comment exécuter le robot

Cliquez sur le bouton "run" en haut de la page pour lancer votre robot dans repl.it.

Si vous écrivez le bot localement, vous pouvez utiliser ces commandes dans le terminal pour exécuter le bot :

Sous Windows :

`py -3 main.py`

Sur d'autres systèmes :

`python3 main.py`

Allez maintenant dans votre salle Discord et tapez "$hello". Votre robot devrait renvoyer "Hello !


## Comment améliorer le bot

Maintenant que nous avons un bot de base qui fonctionne, nous allons l'améliorer. Ce n'est pas pour rien qu'il s'appelle "Encourage Bot".

Ce robot répondra par un message d'encouragement chaque fois que quelqu'un enverra un message contenant un mot triste ou déprimant.

Tout le monde pourra ajouter des messages d'encouragement à l'intention du robot et les messages soumis par les utilisateurs seront stockés dans la base de données Repl.it.

Le robot renverra également une citation inspirante aléatoire à partir d'une API lorsque quelqu'un tapera le message "$inspire" dans le chat.

Nous allons commencer par ajouter la fonctionnalité "$inspire".
### Comment ajouter des citations inspirantes au robot ?

Nous allons obtenir des citations inspirantes à partir d'une API appelée zenquotes.io. Nous devons importer quelques modules Python supplémentaires, ajouter une fonction `get_quote()` et mettre à jour le code de notre robot pour appeler cette fonction.

Voici le code mis à jour. Après le code, je vais expliquer les nouvelles parties.


```python
import discord
import os
import requests
import json

client = discord.Client()

def get_quote():
  response = requests.get("https://zenquotes.io/api/random")
  json_data = json.loads(response.text)
  quote = json_data[0]['q'] + " -" + json_data[0]['a']
  return(quote)

@client.event
async def on_ready():
  print('We have logged in as {0.user}'.format(client))

@client.event
async def on_message(message):
  if message.author == client.user:
    return

  if message.content.startswith('$inspire'):
    quote = get_quote()
    await message.channel.send(quote)

client.run(os.getenv('TOKEN'))

```

Nous devons maintenant importer le module requests. Ce module permet à notre code d'effectuer une requête HTTP pour obtenir des données de l'API. L'API renvoie du JSON, donc le module json facilite le travail avec les données renvoyées.

La fonction `get_quote()` est assez simple. Tout d'abord, elle utilise le module requests pour demander des données à l'URL de l'API. L'API renvoie une citation inspirée aléatoire. Cette fonction peut facilement être réécrite pour obtenir des citations à partir d'une autre API, si l'API actuelle ne fonctionne plus.

Ensuite, dans la fonction, nous utilisons `json.loads()` pour convertir la réponse de l'API en JSON. En procédant par essais et erreurs, j'ai trouvé le moyen d'obtenir le devis du JSON dans le format de chaîne que je voulais. Le devis est renvoyé par la fonction sous la forme d'une chaîne de caractères.

La dernière partie mise à jour dans le code est vers la fin. Auparavant, la fonction recherchait un message commençant par "$hello". Maintenant, elle recherche "$inspire". Au lieu de renvoyer "Hello !", il obtient la citation avec `quote = get_quote()` et renvoie la citation.

À ce stade, vous pouvez exécuter votre code et l'essayer.
## Comment ajouter des messages d'encouragement au robot

Nous allons maintenant implémenter la fonctionnalité qui permet au robot de répondre par des messages d'encouragement lorsqu'un utilisateur publie un message contenant un mot triste.
Comment ajouter des mots tristes au robot

Tout d'abord, nous devons créer une liste Python qui contient les mots tristes auxquels le robot répondra.

Ajoutez la ligne suivante après la création de la variable client :

`sad_words = ["sad", "depressed", "unhappy", "angry", "miserable"]`

N'hésitez pas à ajouter d'autres mots à la liste.
### Comment ajouter des messages d'encouragement au robot

Nous allons maintenant ajouter une liste de messages d'encouragement avec lesquels le robot répondra.

Ajoutez la liste suivante après la liste `sad_words` que vous avez créée :

```py
starter_encouragements = [
  "Cheer up!",
  "Hang in there.",
  "You are a great person / bot!"
]
```


Comme précédemment, n'hésitez pas à ajouter d'autres phrases de votre choix à la liste. Je n'utilise que trois éléments pour l'instant, car nous ajouterons plus tard la possibilité pour les utilisateurs d'ajouter d'autres phrases d'encouragement que le robot pourra utiliser.
### Comment répondre aux messages

Nous devons maintenant mettre à jour notre robot pour utiliser les deux listes que nous avons créées. Tout d'abord, importez le module random car le robot choisira les messages d'encouragement de manière aléatoire. Ajoutez la ligne suivante aux déclarations d'importation en haut du code : import random.

Maintenant, nous allons mettre à jour la fonction `on_message()` pour vérifier tous les messages et voir s'ils contiennent un mot de la liste sad_words. Si un mot triste est trouvé, le robot enverra un message aléatoire d'encouragement.

Voici le code mis à jour :


```py
async def on_message(message):
  if message.author == client.user:
    return

  msg = message.content

  if msg.startswith('$inspire'):
    quote = get_quote()
    await message.channel.send(quote)
    
  if any(word in msg for word in sad_words):
    await message.channel.send(random.choice(starter_encouragements))
```

C'est le bon moment pour tester le bot. Vous en savez maintenant assez pour créer votre propre bot. Vous apprendrez ensuite à mettre en œuvre des fonctionnalités plus avancées et à stocker des données à l'aide de la base de données Repl.it.
### Comment activer les messages soumis par les utilisateurs

Le robot est complètement fonctionnel, mais il faut maintenant faire en sorte qu'il puisse être mis à jour directement depuis Discord. Un utilisateur doit pouvoir ajouter des messages plus encourageants pour que le robot les utilise lorsqu'il détecte un mot triste.

Nous allons utiliser la base de données intégrée de Repl.it pour stocker les messages soumis par les utilisateurs. Cette base de données est un key-value store qui est intégré dans chaque Repl.it.

En haut du code, sous les autres déclarations d'importation, ajoutez from replit import db. Cela nous permettra d'utiliser la base de données Repl.it.

Les utilisateurs pourront ajouter des messages d'encouragement personnalisés que le robot pourra utiliser directement à partir du chat Discord. Avant d'ajouter de nouvelles commandes pour le robot, créons deux fonctions d'aide qui ajouteront des messages personnalisés à la base de données et les supprimeront.

Ajoutez le code suivant après la fonction` get_quote()` :


```py
def update_encouragements(encouraging_message):
  if "encouragements" in db.keys():
    encouragements = db["encouragements"]
    encouragements.append(encouraging_message)
    db["encouragements"] = encouragements
  else:
    db["encouragements"] = [encouraging_message]

def delete_encouragment(index):
  encouragements = db["encouragements"]
  if len(encouragements) > index:
    del encouragements[index]
  db["encouragements"] = encouragements
```

La fonction `update_encouragements()` accepte un message d'encouragement comme argument.

Elle vérifie d'abord si "encouragements" est une clé dans la base de données. Si c'est le cas, elle récupère la liste des encouragements déjà présents dans la base de données, ajoute le nouveau message à la liste, et stocke la liste mise à jour dans la base de données sous la clé "encouragements".

Si la base de données ne contient pas déjà "encouragements", une nouvelle clé de ce nom est créée et le nouveau message d'encouragement est ajouté comme premier élément de la liste.

La fonction `delete_encouragement()` accepte un index comme argument.

Elle récupère la liste des encouragements de la base de données stockée sous la clé "encouragements". Si le nombre d'éléments de la liste des encouragements est supérieur à l'index, l'élément de la liste correspondant à cet index est supprimé.

Enfin, la liste mise à jour est à nouveau stockée dans la base de données sous la clé "encouragements".

Voici le code mis à jour pour la fonction `on_message()`. Après le code, je vais expliquer les nouvelles sections.

```py
async def on_message(message):
  if message.author == client.user:
    return

  msg = message.content
 
  if msg.startswith("$inspire"):
    quote = get_quote()
    await message.channel.send(quote)

  options = starter_encouragements
  if "encouragements" in db.keys():
    options = options + db["encouragements"]

  if any(word in msg for word in sad_words):
    await message.channel.send(random.choice(options))

  if msg.startswith("$new"):
    encouraging_message = msg.split("$new ",1)[1]
    update_encouragements(encouraging_message)
    await message.channel.send("New encouraging message added.")

  if msg.startswith("$del"):
    encouragements = []
    if "encouragements" in db.keys():
      index = int(msg.split("$del",1)[1])
      delete_encouragment(index)
      encouragements = db["encouragements"]
    await message.channel.send(encouragements)
```

La première nouvelle ligne de code ci-dessus est options = starter_encouragements. Nous faisons une copie de starter_encouragements parce que nous allons ajouter les messages soumis par les utilisateurs à cette liste avant de choisir un message aléatoire à envoyer par le robot.

Nous vérifions si "encouragements" figure déjà dans les clés de la base de données (ce qui signifie qu'un utilisateur a soumis au moins un message personnalisé). Si c'est le cas, nous ajoutons les messages de l'utilisateur aux encouragements de départ.

Ensuite, au lieu d'envoyer un message aléatoire depuis starter_encouragements, le robot envoie maintenant un message aléatoire depuis options.

La nouvelle section de code suivante est utilisée pour ajouter un nouveau message soumis par l'utilisateur à la base de données. Si un message Discord commence par "$new", le texte qui suit "$new" sera utilisé comme nouveau message d'encouragement.

Le code msg.split("$new ",1)[1] sépare le message de la commande "$new" et stocke le message dans une variable. Dans cette ligne de code, notez l'espace dans "$new ". Nous voulons tout ce qui se trouve après l'espace.

Nous appelons la fonction d'aide update_encouragements avec le nouveau message, puis le robot envoie un message sur le chat discord pour confirmer l'ajout du message.

La troisième nouvelle section (à la fin du code ci-dessus) vérifie si un nouveau message Discord commence par "$del". Il s'agit de la commande permettant de supprimer un élément de la liste "encouragements" dans la base de données.

D'abord, une nouvelle variable appelée encouragements est initialisée comme un tableau vide. La raison en est que cette section du code enverra un message avec un tableau vide si la base de données ne contient pas de clé "encouragement".

Si la clé "encouragement" se trouve dans la base de données, l'index sera séparé du message Discord en commençant par "$del". Ensuite, la fonction delete_encouragement() est appelée en passant l'index à supprimer. La liste mise à jour des encouragements est chargée dans la variable encouragements, puis le robot envoie un message à Discord avec la liste actuelle.
## Caractéristiques finales du robot

Le robot devrait fonctionner, c'est donc le moment de le tester. Nous allons maintenant ajouter quelques fonctionnalités finales.

Nous allons ajouter la possibilité d'obtenir une liste de messages soumis par les utilisateurs directement depuis Discord et nous allons ajouter la possibilité de désactiver ou d'activer la réponse du robot aux mots tristes.

Je vais vous donner le code final complet du programme, puis je discuterai des mises à jour sous le code.


```py
import discord
import os
import requests
import json
import random
from replit import db

client = discord.Client()

sad_words = ["sad", "depressed", "unhappy", "angry", "miserable"]

starter_encouragements = [
  "Cheer up!",
  "Hang in there.",
  "You are a great person / bot!"
]

if "responding" not in db.keys():
  db["responding"] = True

def get_quote():
  response = requests.get("https://zenquotes.io/api/random")
  json_data = json.loads(response.text)
  quote = json_data[0]["q"] + " -" + json_data[0]["a"]
  return(quote)

def update_encouragements(encouraging_message):
  if "encouragements" in db.keys():
    encouragements = db["encouragements"]
    encouragements.append(encouraging_message)
    db["encouragements"] = encouragements
  else:
    db["encouragements"] = [encouraging_message]

def delete_encouragment(index):
  encouragements = db["encouragements"]
  if len(encouragements) > index:
    del encouragements[index]
  db["encouragements"] = encouragements

@client.event
async def on_ready():
  print("We have logged in as {0.user}".format(client))

@client.event
async def on_message(message):
  if message.author == client.user:
    return

  msg = message.content

  if msg.startswith("$inspire"):
    quote = get_quote()
    await message.channel.send(quote)

  if db["responding"]:
    options = starter_encouragements
    if "encouragements" in db.keys():
      options = options + db["encouragements"]

    if any(word in msg for word in sad_words):
      await message.channel.send(random.choice(options))

  if msg.startswith("$new"):
    encouraging_message = msg.split("$new ",1)[1]
    update_encouragements(encouraging_message)
    await message.channel.send("New encouraging message added.")

  if msg.startswith("$del"):
    encouragements = []
    if "encouragements" in db.keys():
      index = int(msg.split("$del",1)[1])
      delete_encouragment(index)
      encouragements = db["encouragements"]
    await message.channel.send(encouragements)

  if msg.startswith("$list"):
    encouragements = []
    if "encouragements" in db.keys():
      encouragements = db["encouragements"]
    await message.channel.send(encouragements)
    
  if msg.startswith("$responding"):
    value = msg.split("$responding ",1)[1]

    if value.lower() == "true":
      db["responding"] = True
      await message.channel.send("Responding is on.")
    else:
      db["responding"] = False
      await message.channel.send("Responding is off.")

client.run(os.getenv("TOKEN"))
```

La première section ajoutée au code se trouve juste en dessous de la liste des encouragements au démarrage :

```py
if "responding" not in db.keys():
  db["responding"] = True
```

Nous créons une nouvelle clé dans la base de données appelée "responding" et lui attribuons la valeur "True". Nous allons l'utiliser pour déterminer si le robot doit répondre aux mots tristes ou non. Comme la base de données est sauvegardée même après l'arrêt du programme, nous ne créons la nouvelle clé que si elle n'existe pas déjà.

La nouvelle partie suivante du code est que la section qui répond aux mots tristes est maintenant à l'intérieur de cette instruction if : if db["responding"] :. Le robot ne répondra aux mots tristes que si db["responding"] = True. La possibilité de mettre à jour cette valeur vient après la section suivante.

Ensuite, après le code pour que le robot réponde à la commande "$del", il y a un nouveau code pour répondre à la commande "$list" lorsqu'elle est envoyée comme message Discord.

Cette section commence par la création d'une liste vide appelée encouragements. Ensuite, s'il existe déjà des encouragements dans la base de données, ceux-ci remplacent la liste vide qui vient d'être créée.

### Enfin, le robot envoie la liste des encouragements sous forme de message Discord.

La dernière nouvelle section vient ensuite. Ce code permet au robot de répondre à la commande "$responding". Cette commande prend comme argument "true" ou "false". Voici un exemple d'utilisation : "$responding true".

Le code extrait d'abord l'argument avec value = msg.split("$responding ",1)[1] (comme précédemment, notez l'espace dans "$responding "). Il y a ensuite une instruction if/else qui définit de manière appropriée la clé "responding" dans la base de données et envoie un message de notification à Discord. Si l'argument est autre que "true", le code suppose "false".

Le code du robot est terminé ! Vous pouvez maintenant exécuter le robot et l'essayer. Mais il reste une étape importante que nous allons aborder.
Comment configurer le robot pour qu'il fonctionne en continu ?

Si vous exécutez votre robot dans repl.it et que vous fermez ensuite l'onglet dans lequel il est exécuté, il s'arrête.

Mais il y a deux façons de le faire fonctionner en continu, même après avoir fermé le web bowser.

Le premier moyen, et le plus simple, est de souscrire à un plan payant sur Repl.it. Le plan payant le moins cher s'appelle le plan Hacker et comprend cinq robots toujours actifs.

Vous pouvez obtenir trois mois gratuits en utilisant ce lien (limité aux 1000 premières personnes) : https://repl.it/claim?code=tryalwayson2103.

Une fois que vous vous êtes inscrit à ce plan, ouvrez votre Repl et cliquez sur le nom en haut. Sélectionnez ensuite l'option "Always On".


Il existe un autre moyen de maintenir l'exécution de votre code, même avec le plan gratuit, mais il est un peu plus compliqué. Repl.it continuera à exécuter un serveur web même après la fermeture de l'onglet. Mais même un serveur web ne fonctionnera que pendant une heure sans aucune utilisation.

### Voici ce que dit la documentation de repl.it :

> Une fois déployé, le serveur continuera à fonctionner en arrière-plan, même après la fermeture de l'onglet du navigateur. Le serveur restera éveillé et actif jusqu'à une heure après sa dernière requête, après quoi il entrera dans une phase de sommeil. Les repls en sommeil seront réveillés dès qu'ils recevront une autre demande ; il n'est pas nécessaire de relancer le repl. Cependant, si vous effectuez des changements sur votre serveur, vous devrez relancer le repl pour que ces changements soient reflétés dans la version live.

Pour assurer le fonctionnement continu du robot, nous utiliserons un autre service gratuit appelé Uptime Robot à l'adresse https://uptimerobot.com/.

Uptime Robot peut être configuré pour envoyer un ping au serveur web du bot sur repl.it toutes les 5 minutes. Avec des pings constants, le bot n'entrera jamais en phase de sommeil et continuera à fonctionner.

Il nous reste donc deux choses à faire pour que notre robot fonctionne en continu :

    créer un serveur web dans repl.it et
    configurer Uptime Robot pour qu'il envoie continuellement des pings au serveur web.

### Comment créer un serveur web dans repl.it ?

La création d'un serveur web est plus simple que vous ne le pensez.

Pour le faire, créez un nouveau fichier dans votre projet appelé keep_alive.py.

Ajoutez ensuite le code suivant :


```py
from flask import Flask
from threading import Thread

app = Flask('')

@app.route('/')
def home():
    return "Hello. I am alive!"

def run():
  app.run(host='0.0.0.0',port=8080)

def keep_alive():
    t = Thread(target=run)
    t.start()

```

Dans ce code, nous utilisons Flask pour démarrer un serveur web. Le serveur renvoie "Hello. Je suis vivant." à toute personne qui le visite. Le serveur fonctionne sur un thread distinct de celui de notre robot. Nous ne discuterons pas de tout ici puisque le reste n'est pas vraiment pertinent pour notre bot.

Il ne nous reste plus qu'à faire tourner le serveur web dans le robot.

Ajoutez la ligne suivante en haut du fichier main.py pour importer le serveur.

```from keep_alive import keep_alive```

Pour démarrer le serveur web lors de l'exécution de main.py, ajoutez la ligne suivante en avant-dernière ligne, juste avant l'exécution du bot.

`keep_alive()`

Lorsque vous lancez le bot sur repl.it après avoir ajouté ce code, une nouvelle fenêtre de serveur Web s'ouvre. Une URL est affichée pour le serveur Web. Copiez l'URL pour pouvoir l'utiliser dans la section suivante.

### Comment configurer Uptime Robot

Maintenant nous devons configurer Uptime Robot pour qu'il envoie un ping au serveur web toutes les cinq minutes. Cela permettra au robot de fonctionner en continu.

Créez un compte gratuit sur https://uptimerobot.com/.

Une fois que vous êtes connecté à votre compte, cliquez sur "Add New Monitor".


Pour le nouveau moniteur, sélectionnez "HTTP(s)" comme type de moniteur et nommez-le comme vous le souhaitez. Ensuite, collez l'URL de votre serveur web depuis repl.it. Enfin, cliquez sur "Créer un moniteur".


Nous avons terminé ! Maintenant, le robot va fonctionner en continu pour que les gens puissent toujours interagir avec lui sur Repl.it.
## Conclusion

Vous savez maintenant comment créer un robot Discord avec Python, et le faire fonctionner en continu dans le cloud.

Il y a beaucoup d'autres choses que la bibliothèque discord.py peut faire. Si vous souhaitez doter votre robot Discord d'encore plus de fonctionnalités, la prochaine étape consiste à consulter la documentation de discord.py.