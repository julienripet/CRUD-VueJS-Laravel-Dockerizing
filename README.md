# CRUD Articles

## A propos

Ce repo est le parent de deux autres, [un frontend](https://github.com/julienripet/CRUD-VueJS-Laravel-Frontend) et [un backend](https://github.com/julienripet/CRUD-VueJS-Laravel-Backend). Il contient le fichier `docker-compose.yml`, qui permet de lancer rapidement les deux cotés de l'application grâce à Docker, ainsi que d'attacher automatiquement un container MariaDB pour le stockage des données. Son utilisation n'est pas obligatoire, mais facilite et accélère son lancement.

L'application en elle-même est un test technique, servant à démontrer ma capacité à créer une API Rest sur Laravel, et un site web capable d'interagir avec, créé avec Vue.js.

## Mise en place

Pour mettre en place l'application en utilisant ce repo, vous aurez besoin du terminal de votre choix, de [Git](https://git-scm.com/downloads), de [Docker Compose](https://docs.docker.com/compose/install/), et de [Node.js](https://nodejs.org/en/) .

Commencez par cloner ce repo en entrant la commande suivante dans votre terminal:

```bash
git clone https://github.com/julienripet/CRUD-VueJS-Laravel-Dockerizing
```

Cette commande va créer un nouveau dossier, et récuperer le fichier `docker-compose.yml` nécessaire à l'utilisation de Docker.

Entrez dans ce dossier en tapant `cd CRUD-VueJS-Laravel-Dockerizing`, puis cloner les deux repos "enfants" avec :

```bash
git clone https://github.com/julienripet/CRUD-VueJS-Laravel-Backend
git clone https://github.com/julienripet/CRUD-VueJS-Laravel-Frontend
```

Une fois les deux repos créés, vous pouvez lancez les containers Docker avec la commande :

```bash
docker compose up -d
```

A cause d'un problème avec le CLI de Vue.js v3, vous devrez forcer l'installation des modules en entrant la commande:

```bash
cd CRUD-VueJS-Laravel-Frontend && npm i
```

Après cette étape, vous devriez pouvoir ouvrir [le site](http://localhost:8080) dans votre navigateur.

## Seeding de la base de données

Pour rendre les tests plus simples, un Seeder Laravel a été créé, afin de remplir la base de données avec des infos factices.
Chaque appel à ce Seeder remplira la base de données de 10 articles supplémentaires, générés aléatoirement.
Pour ce faire, entrez dans le dossier du backend avec `cd CRUD-VueJS-Laravel-Backend` puis entrez la commande suivante :

```bash
docker exec crud-vuejs-laravel-dockerizing_backend_1 php artisan db:seed
```

Au cas où le serveur vous répond que l'application est en production, créez un fichier .env à partir du ficher .env.example :

```bash
docker exec crud-vuejs-laravel-dockerizing_backend_1 cp .env.example .env
```

## Fonctionnement de l'application

L'application est assez simple en soi. L'unique page qui la compose affiche, dans un tableau, les articles sauvegardés en base de données.  Ce tableau peut être filtré et trié à l'aide des entêtes de colonnes, ainsi qu'à l'aide de la barre de recherche. Un filtre global permet également d'afficher les articles archivés si on le désire.

Chaque rangée représente un article, affichant son libellé, son état, son type, son numéro de série, sa date de création et de modification, et son état d'archivage.  Chaque article est modifiable et supprimable grâce aux deux boutons de fin de rangée.

Un nouvel article peut être ajouté à tout moment en cliquant sur le bouton "Créer un nouvel Article". Une popup apparaît alors, dans laquelle on va pouvoir renseigner les champs requis.

## Amélioration

Les améliorations possibles que je verrais, sans ordre particulier

1. Ajout de comptes utilisateurs  
Des comptes pour chaque utilisateur de l'application pourraient être implémentés, requérant un login et un mot de passe, et créant ainsi un lien entre utilisateur et article.

2. Amélioration du coté responsive du tableau des articles  
Actuellement, les articles ne peuvent être filtrés ou triés sur mobile

3. Ajout d'un routeur à Vue.js  
Afin d'en faire une véritable SPA, un routeur avec de multiples pages serait nécessaire

4. Un mode hors-ligne  
Ajouter la capacité à l'application de storer les articles dans un storage local, en cas de déconnexion, puis de mise à jour automatique lors du retour en ligne.

5. Créer des containers Docker optimisés pour la mise en production  
Ce qui permettrait de réduire la taille des containers, et d'améliorer leur sécurité
