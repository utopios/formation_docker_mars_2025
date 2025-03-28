

## 🧪 Sujet d’exercice – Docker Compose multi-services avec réseaux et volumes

---

### 🎯 Objectif :

Vous disposez de **trois applications** (avec leurs **Dockerfiles fournis**) et de **deux services de base de données**. Votre tâche est de réaliser un **fichier `docker-compose.yml`** permettant de lancer l’ensemble de l’infrastructure avec les bonnes dépendances, réseaux, et volumes.

---

### 🧩 Description des services :

#### 🔹 Partie 1 – Service `vote` (frontend de vote)
- Localisation : `./vote`
- Application Flask (Python)
- Démarrée avec `gunicorn`
- Dépend de la base Redis
- Doit être connectée au **réseau `front`**

#### 🔹 Partie 2 – Service `result` (frontend de résultat)
- Localisation : `./result`
- Application Node.js
- Démarrée avec `node server.js`
- Dépend de la base PostgreSQL
- Doit être connectée au **réseau `front`**

#### 🔹 Partie 3 – Service `worker`
- Localisation : `./worker`
- Application C# (.NET Core)
- Nécessite une phase de build puis d’exécution
- Se connecte à Redis et PostgreSQL
- Doit être connecté au **réseau `back`**

#### 🔹 Partie 4 – Service Redis
- Image : `redis:5.0-alpine3.10`
- Doit être connecté au **réseau `back`**

#### 🔹 Partie 5 – Service PostgreSQL
- Image : `postgres:9.4`
- Doit être connecté au **réseau `back`**
- Un **volume** doit être utilisé pour persister les données

---

### 📌 Contraintes pour le `docker-compose.yml` à produire :

1. Les **Dockerfiles sont fournis** pour les services `vote`, `result`, et `worker` – **vous ne devez pas les créer**.
2. Vous devez :
   - Créer les **services** dans le fichier `docker-compose.yml`.
   - Configurer deux **réseaux `bridge` personnalisés** : `front` et `back`.
   - Placer :
     - `vote` et `result` dans le réseau `front`
     - `worker`, `redis`, et `postgres` dans le réseau `back`
   - Définir des **volumes nommés** pour la base PostgreSQL.
   - Ajouter les **commandes de démarrage personnalisées** pour chaque service.

Souhaites-tu aussi un squelette de `docker-compose.yml` à compléter pour tes apprenants ou un corrigé dans un fichier à part ?