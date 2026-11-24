# MyAppReact - Docker et Docker Compose

## 1. Présentation du projet

Ce projet consiste à conteneuriser une application MERN composée de trois services :
- Frontend : React
- Backend : Node.js et Express
- Base de données : MongoDB

## 2. Technologies utilisées

- React
- Node.js
- Express
- MongoDB
- Docker
- Docker Compose

## 3. Dockerisation du Backend

Le fichier Dockerfile du serveur se trouve dans le dossier `Server`.

Construction de l'image :

```bash
docker build -t mern-server ./Server
```

## 4. Dockerisation du Frontend

Le fichier Dockerfile du client se trouve dans le dossier `Client`.

Construction de l'image :

```bash
docker build -t mern-client ./Client
```

## 5. Création du réseau Docker

```bash
docker network create mern-network
```

## 6. Exécution avec Docker Compose

Pour construire les images et démarrer les services :

```bash
docker compose up --build
```

## 7. Vérification des conteneurs

```bash
docker compose ps
```

## 8. Accès aux services

- Frontend : http://localhost:3000
- Backend : http://localhost:9000
- MongoDB : port 27017

## 9. Arrêt des services

```bash
docker compose down
```