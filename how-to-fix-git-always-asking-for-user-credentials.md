# Comment corriger le fait que Git demande toujours les informations d'identification de l'utilisateur ?

![img cover](https://www.freecodecamp.org/news/content/images/size/w2000/2020/05/article-banner--10-.png)

## Avez-vous déjà rencontré Git vous demandant votre nom d'utilisateur et votre mot de passe à chaque fois que vous essayez d'interagir avec GitHub, même après l'avoir configuré ? Eh bien, c'est un problème très courant parmi les utilisateurs qui utilisent l'URL de clone HTTPS pour leur dépôt. Dans cet article, je vais vous montrer comment résoudre ce problème.

Les URLs de clonage ==https://== sont disponibles sur tous les dépôts publics et privés. Ces URLs fonctionnent partout, même si vous êtes derrière un pare-feu ou un proxy.

![img step1Alt](https://www.freecodecamp.org/news/content/images/2019/10/clone.png)
 
Lorsque vous interagissez avec un dépôt distant en utilisant des URL HTTPS en ligne de commande, on vous demande votre nom d'utilisateur et votre mot de passe GitHub, c'est nul, non ?

Eh bien, l'utilisation d'une URL HTTPS distante a quelques avantages : elle est plus facile à configurer que SSH :), et fonctionne généralement à travers des pare-feu et des proxies stricts. Cependant, elle vous demande également d'entrer vos identifiants GitHub à chaque fois que vous tirez ou poussez un dépôt :(.
## Vous pouvez résoudre ce problème en configurant Git pour qu'il stocke votre mot de passe pour vous.

Voici comment procéder :

+ Mettre à jour l'URL de l'origine distante en utilisant SSH au lieu de HTTP

``` git
git remote set-url origin git@github.com:username/repo.git
```
ou

+ Faites en sorte que Git stocke le nom d'utilisateur et le mot de passe et il ne les demandera jamais.
+ 
``` git
git config --global credential.helper store
```

+ Sauvegarder le nom d'utilisateur et le mot de passe pour une session (le mettre en cache) ;
``` git
git config --global credential.helper cache
```

+ Vous pouvez également définir un délai d'attente pour le paramètre ci-dessus

``` git
git config --global credential.helper 'cache --timeout=600' (en anglais)
```
Bingo, vous venez de régler le problème, Git ne vous demandera plus jamais vos informations d'identification.

## CONCLUSION

Cependant, pour des raisons de sécurité, il est conseillé d'utiliser SSH pour interagir avec GitHub, surtout si vous travaillez pour une entreprise ou si vous utilisez un ordinateur qui n'est pas le vôtre.

En utilisant le protocole SSH, vous pouvez vous connecter à GitHub sans avoir à fournir votre nom d'utilisateur ou votre mot de passe à chaque fois.

Apprenez comment vous connecter à GitHub avec SSH [ici](https://help.github.com/en/articles/connecting-to-github-with-ssh).

### Auteur: Bolaji Ayodeji 
#### Titre: Software Engineer, Content Creator & Developer Advocate.

