Vous avez fait votre première connexion à Travis et SonarCloud, bien joué !

Nouvelle étape, vous avez différents services qui fonctionnent (httpd, simple-api, database, cf dossiers).
Essayer de les lancer sur votre machine via le `docker-compose.yml` présent.
Tout doit fonctionner.

L'idée va être de construire chaque image, de l'envoyer sur Docker Hub
puis de déployer les changements sur le serveur distant.

Pour commencer, vous devez ajouter les fichiers à votre dépôt Git et faire une nouvelle CI
qui va :

1. Build chaque image et la push sur DockerHub (une étape par service)
2. Utiliser Ansible pour :
   - Installer Docker sur votre serveur (vps)
   - Installer docker-compose sur votre serveur
   - ouvrir le port spécifique (80) sur votre serveur
   - installer le dernier `docker-compose.yaml` sur votre serveur
   - relancer le docker-compose sur votre serveur
