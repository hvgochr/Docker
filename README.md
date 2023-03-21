# TP Docker Partie 1

Ce projet contient une configuration Docker Compose pour exécuter les services suivants:

- `web89` : un serveur Web Apache avec PHP 8.2
- `mysql` : un serveur de base de données MySQL 5.7
- `phpmyadmin` : une interface Web pour administrer la base de données MySQL
- `postgres` : un serveur de base de données PostgreSQL avec PostGIS
- `pgadmin` : une interface Web pour administrer la base de données PostgreSQL

## Prérequis:

Avant de pouvoir exécuter cette configuration Docker Compose, vous devez avoir Docker et Docker Compose installés sur votre système.

Docker : https://docs.docker.com/engine/install/
Docker Compose : https://docs.docker.com/compose/install/

## Utilisation

Clonez le projet dans votre répertoire local :

```bash
git clone https://github.com/hvgochr/Docker
```

Placez-vous dans le répertoire du projet :

```bash
cd Docker
```

Lancez les services en arrière-plan :

```bash
docker compose build
docker compose up -d
```

Accédez aux interfaces Web :
- http://localhost:82 : site Web Apache
- http://localhost:83 : interface Web de phpMyAdmin
- http://localhost:8080 : interface Web de pgAdmin

## Arrêt

Pour arrêter les services, exécutez la commande suivante dans le répertoire du projet :

```bash 
docker compose down
```

Cela arrêtera tous les services et supprimera les conteneurs et les réseaux associés.

## Notes

Les volumes sont utilisés pour stocker les données persistantes de MySQL, PostgreSQL et pgAdmin. Les données sont stockées dans les répertoires suivants:

./docker/html : contenu du site Web Apache
./Docker/mysql : données MySQL
./docker/data : données PostgreSQL
./docker/pgadmin : données pgAdmin

La base de données PostgreSQL est configurée pour utiliser l'extension PostGIS. Cette extension est installée via la commande CREATE EXTENSION postgis; dans le fichier docker-compose.yml.

Les noms d'utilisateur et les mots de passe pour MySQL et PostgreSQL sont définis dans le fichier docker-compose.yml.

Les ports exposés pour chaque service sont définis dans le fichier docker-compose.yml.

Les variables d'environnement pour pgAdmin sont définies dans le fichier docker-compose.yml.
