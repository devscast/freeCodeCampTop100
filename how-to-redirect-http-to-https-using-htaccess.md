https://www.freecodecamp.org/news/how-to-redirect-http-to-https-using-htaccess

# Comment rediriger HTTP vers HTTPS en utilisant .htaccess

Chrome et Firefox ont commencé à afficher des avertissements d'insécurité sur les sites sans certificat SSL. Sans SSL, votre site Web sera considéré comme non sécurisé par les visiteurs. Il est donc nécessaire d'utiliser une connexion cryptée SSL pour des raisons de sécurité, d'accessibilité ou de conformité PCI. Il devient très important de rediriger de HTTP à HTTPS.

![](https://cdn-media-1.freecodecamp.org/images/0*wUTFJrRSM2vh1H7v.jpg)

## Qu'est-ce que le SSL ?

SSL (Secure Sockets Layer) est un protocole de sécurité standard pour établir des liens cryptés entre un serveur web et un navigateur dans une communication en ligne.

L'utilisation de la technologie SSL garantit que toutes les données transmises entre le serveur web et le navigateur restent cryptées.

Un **certificat SSL** est nécessaire pour créer une connexion SSL. Vous devez fournir tous les détails concernant l'identité de votre site web et de votre entreprise lorsque vous choisissez d'activer SSL sur votre serveur web. Ensuite, deux clés cryptographiques sont créées - une clé privée et une clé publique.

[En savoir plus : Pourquoi SSL est essentiel ?](https://www.sslrenewals.com/blog/why-is-ssl-important-benefits-of-using-ssl-certificate)

Pour forcer votre trafic Web à utiliser le protocole HTTPS, modifiez les codes dans le fichier **.htaccess**.

Avant de passer à la redirection de HTTP vers HTTPS, voici comment modifier le fichier .htaccess. Si vous le savez déjà, passez directement aux étapes de redirection.

## Modification du fichier .htaccess

Le fichier .htaccess contient des instructions/directives qui indiquent au serveur comment agir dans certains scénarios et qui ont une incidence directe sur le fonctionnement de votre site Web. Directives courantes dans le fichier .htaccess :

- Redirections
- Réécriture d'URL

### Façons de modifier un fichier .htaccess :

1. Modifiez le fichier sur votre ordinateur et téléchargez-le sur le
   serveur en utilisant le FTP.
2. Utilisez le mode "Édition" du programme FTP qui vous permet de modifier un fichier à distance.
3. Utilisez un éditeur de texte et SSH pour modifier le fichier.
   Utilisez le gestionnaire de fichiers de cPanel pour modifier le
   fichier.

## Modification du fichier .htaccess dans le gestionnaire de fichiers de cPanel

**Note :** Sauvegardez votre site web au cas où quelque chose ne fonctionnerait pas.

1. Connectez-vous à cPanel
2. Fichiers > Gestionnaire de fichiers > Racine du document pour :
3. Sélectionnez maintenant le nom de domaine auquel vous voulez accéder
4. Cochez "Show Hidden Files (dotfiles)".
5. Cliquez sur "Go".
6. Après l'ouverture d'un nouvel onglet ou d'une nouvelle fenêtre, recherchez le fichier .htaccess.
7. Faites un clic droit sur le fichier .htaccess et cliquez sur "Code Edit" dans le menu.
8. Il se peut qu'une boîte de dialogue apparaisse pour vous demander quel est le codage. Cliquez sur le bouton "Éditer" pour continuer.
9. Modifiez le fichier
10. "Enregistrez les modifications lorsque vous avez terminé.
11. Testez votre site Web pour vous assurer que tout est fait correctement. En cas d'erreur, rétablissez la version précédente et réessayez
12. Une fois que vous avez terminé, cliquez sur "Fermer" pour fermer la fenêtre.

## 2. Redirection de HTTP vers HTTPS

### 1. Rediriger tout le trafic Web

Si vous avez du code existant dans votre .htaccess, ajoutez ce qui suit :
```
RewriteEngine On
RewriteCond %{SERVER_PORT} 80
RewriteRule ^(.*)$ https://www.yourdomain.com/$1 [R,L]
```

### 2. Rediriger uniquement un domaine spécifique

Pour rediriger un domaine spécifique afin d'utiliser HTTPS, ajoutez ce qui suit :

```
RewriteEngine On
RewriteCond %{HTTP_HOST} ^yourdomain\.com [NC]
RewriteCond %{SERVER_PORT} 80
RewriteRule ^(.*)$ https://www.yourdomain.com/$1 [R,L]
```

### 3. Rediriger uniquement un dossier spécifique

Pour rediriger vers HTTPS sur un dossier spécifique, ajoutez ce qui suit :

```
RewriteEngine On
RewriteCond %{SERVER_PORT} 80
RewriteCond %{REQUEST_URI} folder
RewriteRule ^(.*)$ https://www.yourdomain.com/folder/$1 [R,L]
```

Remarque : Remplacez *`"votredomaine"`* par votre nom de domaine réel lorsque cela est nécessaire. De même, dans le cas du dossier, remplacez `/folder` par le nom du dossier.

Vous pensez que cet article vous a été utile ? Partagez cet article pour aider les autres à passer au HTTPS.

![](https://cdn-media-1.freecodecamp.org/images/0*P6EKtlMMzyIXNRMw.png)