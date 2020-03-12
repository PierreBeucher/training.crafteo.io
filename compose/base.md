# Docker Compose - basics

Nous utiliserons l'application Example Voting App pour l'exercice, pour obtenir le code source:

```
git clone -b img-build https://gitlab.com/crafteo/training/example-voting-app
```

## Exercices

### Lancement d'une stack Docker Compose

`docker-compose.yml` contiens une base de fichier Docker Compose pour la Voting App avec les services DB, Worker & Result (Vote et Redis ne sont pas encore implémentés de façon volontaire)

- Utiliser la CLI `docker-compose` pour lancer la stack en mode détachée
- Accéder au service Result selon le port ouvert défini par la configuration Docker Compose. 

### Configuration de services Docker Compose

Ajouter les services Redis et Vote tels que:

- Redis
  - utilise l'image `redis:alpine`
  - container nommé `redis`
- Vote 
  - utilise l'image `registry.gitlab.com/crafteo/training/example-voting-app/vote`
  - container nommé `vote`
  - expose le port `8080` sur `5000` 
  
Et relancer l'application

- le service vote doit être accessible sur `localhost:5000`
- le service Redis doit être lancé
- un vote via le service Vote doit être visible via le service Result

