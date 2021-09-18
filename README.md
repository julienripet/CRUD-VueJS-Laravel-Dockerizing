# CRUD Articles

## A propos

Ce repo est le parent de deux autres, [un frontend](https://github.com/julienripet/CRUD-VueJS-Laravel-Frontend) et [un backend](https://github.com/julienripet/CRUD-VueJS-Laravel-Backend). Il contient le fichier `docker-compose.yml`, qui permet de lancer rapidement les deux cotés de l'application grâce à Docker, ainsi que d'attacher automatiquement un container MariaDB pour le stockage des données. Son utilisation n'est pas obligatoire, mais facilite et accèlere son lancement.

L'application en elle-même est un test technique, servant à démontrer ma capacité à créer une API Rest sur Laravel, et un site web capable d'interagir avec, créé avec Vue.js.

## Mise en place

Pour mettre en place l'application en utilisant ce repo, vous aurez besoin du terminal de votre choix, de [Git](https://git-scm.com/downloads) et de [Docker Compose](https://docs.docker.com/compose/install/).

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

Après cette étape, vous devriez pouvoir ouvrir [le site](http://localhost:8080) dans votre navigateur.
