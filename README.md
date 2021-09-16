# CRUD Articles

## A propos

Ce repo est le parent de deux autres, [un frontend](https://github.com/julienripet/CRUD-VueJS-Laravel-Frontend) et [un backend](https://github.com/julienripet/CRUD-VueJS-Laravel-Backend). Il contient le fichier `docker-compose.yml`, qui permet de lancer rapidement les deux cotés de l'application grâce à Docker. Son utilisation n'est pas obligatoire, mais facilite et accèlere son lancement.

L'application en elle-même est un test technique, servant à démontrer ma capacité à créer une API Rest sur Laravel, et un site web capable d'interagir avec, créé avec VueJs.

## Mise en place

Pour mettre en place l'application en utilisant ce repo, vous aurez besoin du terminal de votre choix, de [Git](https://git-scm.com/downloads) et de [Docker Compose](https://docs.docker.com/compose/install/).

Commencez par cloner les deux repos "enfants" dans un dossier de votre choix, en entrant les commandes suivantes dans votre terminal :

```bash
git clone https://github.com/julienripet/CRUD-VueJS-Laravel-Backend
git clone https://github.com/julienripet/CRUD-VueJS-Laravel-Frontend
```

Une fois les deux repos créés, vous pouvez lancez les containers Docker avec la commande :

```bash
docker compose up -d
```

Après cette étape, vous devriez pouvoir ouvrir [le site](http://localhost:8080) dans votre navigateur.
