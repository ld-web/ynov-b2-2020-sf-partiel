# Ynov - B2 - Symfony - Partiel

Vous allez réaliser une bibliothèque musicale.

## Entités

### Artist

| Champ | Type | Commentaire |
|---|---|---|
|id|int||
|name|string||
|picture|string|Image représentant l'artiste|
|style|ManyToOne| Le style de l'artiste (**un style par artiste pour faire plus simple**) |

### Style

| Champ | Type | Commentaire |
|---|---|---|
|id|int||
|name|string||
|artists|OneToMany| Les artistes de ce style |

### Album

| Champ | Type | Commentaire |
|---|---|---|
|id|int||
|name|string||
|releaseYear|int |L'année de sortie de l'album |
|cover|string| La pochette de l'album |
|artist|ManyToOne| L'artiste qui a réalisé l'album |

> Pas besoin de créer l'entité représentant les titres de l'album

## Authentification

Vous créerez une entité utilisateur comme vu en cours.

Le champ d'identification sera un champ `login`, qui représentera le nom d'utilisateur.

## Pages

Les pages seront constituées d'un menu de navigation et d'un contenu.

Eléments du menu :

- Accueil
- Artistes
- Connexion

### Accueil

La page d'accueil présentera les 30 derniers albums : vous afficherez une liste des albums ordonnée par l'année de sortie, la plus récente en premier.

> Vu que nous n'avons pas les morceaux des albums, vous pouvez, pour chaque album, mettre un lien vers l'artiste à la place. En gros, pas besoin de faire de page album

### Artistes

Affichez sur cette page tous les artistes enregistrés.

Chaque élément de la liste présentera un **lien** vers la fiche artiste.

### Page Artiste

La fiche artiste présentera 3 sections :

- Informations de l'artiste (nom, image, style)
- Liste de tous ses albums
- Artistes similaires

"artistes similaires" : récupérez et affichez des liens vers les artistes du même style.

### Administration

Toutes les pages de l'interface d'administration commenceront par `/admin`.

Elles seront uniquement accessible au rôle `ROLE_ADMIN` de l'application.

Dans l'interface d'administration, générez un CRUD pour les styles, les artistes, et les albums.

Il s'agira d'adapter les formulaires générés par Symfony pour implémenter l'upload de fichiers pour l'image de l'artiste et la couverture de l'album, et les listes déroulantes pour le style dans l'artiste, et l'artiste dans l'album.

## Bonus 1

A l'aide de la variable globale Twig `app` fournie par Symfony, adaptez le menu pour afficher les éléments pertinents en fonction de la situation (utilisateur non connecté ? Alors on affiche "Connexion", sinon "Déconnexion" et un petit lien vers l'administration par exemple).

Vous pouvez également faire apparaître le login de l'utilisateur dans la barre de menu s'il est connecté.

## Bonus 2

Créez un moteur de recherche d'artistes, par le nom de l'artiste.

Vous êtes libre sur l'apparence et l'implémentation.
