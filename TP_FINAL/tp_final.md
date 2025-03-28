### Mise en place d’un environnement Symfony avancé avec Docker Compose

**Objectif :**

Déployer un environnement de développement complet pour une application Symfony, incluant les services essentiels tels que MySQL, PHP-FPM, Nginx, Elasticsearch, Logstash, Kibana, et PhpMyAdmin. L’objectif est de configurer ces services pour qu’ils interagissent correctement, tout en respectant les bonnes pratiques de sécurité et d’efficacité.

Contexte :

Vous êtes chargé de mettre en place un environnement multi-services pour une application Symfony. Cet environnement doit inclure :
	•	Une base de données MySQL.
	•	Un serveur PHP-FPM pour exécuter le code PHP avec prise en charge de Xdebug.
	•	Un serveur Nginx pour exposer l’application web.
	•	Une interface PhpMyAdmin pour gérer la base de données.
	•	Une stack ELK (Elasticsearch, Logstash, Kibana) pour la gestion des logs.

L’infrastructure doit être orchestrée à l’aide de Docker Compose.

Travail demandé :
	1.	Création du fichier docker-compose.yml :
	•	Configurez un fichier docker-compose.yml contenant les services mentionnés.
	•	Définissez les variables d’environnement nécessaires et placez-les dans un fichier .env.
	2.	Services à configurer :
	•	MySQL :
	•	Configurez une base de données avec un utilisateur, un mot de passe, et une base par défaut.
	•	Exposez le port de la base de données sur l’hôte.
	•	Ajoutez un volume pour la persistance des données.
	•	PHP-FPM :
	•	Construisez une image personnalisée basée sur une configuration PHP adaptée à Symfony.
	•	Configurez Xdebug pour permettre le débogage.
	•	PhpMyAdmin :
	•	Ajoutez un conteneur pour PhpMyAdmin pour gérer la base de données via une interface web.
	•	Connectez PhpMyAdmin au service MySQL.
	•	Nginx :
	•	Construisez une image personnalisée Nginx pour servir l’application Symfony depuis le répertoire public.
	•	Exposez le service sur le port 80.
	•	ELK (Elasticsearch, Logstash, Kibana) :
	•	Déployez Elasticsearch pour l’indexation et la recherche.
	•	Configurez Logstash pour collecter et analyser les logs.
	•	Ajoutez Kibana pour visualiser les données issues de Logstash.
	3.	Bonnes pratiques :
	•	Stockez toutes les informations sensibles dans un fichier .env (mot de passe MySQL, variables Xdebug, etc.).
	•	Exécutez les services avec des utilisateurs non-root lorsque possible.
	•	Limitez les permissions des volumes et configurez-les en lecture seule là où applicable.
	•	Ajoutez des healthcheck pour surveiller l’état des services critiques (MySQL, Elasticsearch, PHP-FPM, etc.).
	•	Configurez les limites de ressources (CPU et mémoire) pour chaque service.
	4.	Dossier et fichiers supplémentaires :
	•	Ajoutez les fichiers nécessaires pour construire les images personnalisées (par exemple : Dockerfile pour PHP-FPM et Nginx).
	•	Fournissez les fichiers de configuration pour Logstash (pipelines.yml, fichiers dans conf.d).
	•	Documentez la configuration de Nginx et de Xdebug.
	5.	Démarrage et test :
	•	Démarrez l’ensemble des services en utilisant Docker Compose.
	•	Vérifiez que tous les services communiquent correctement :
	•	L’application Symfony est accessible sur http://localhost.
	•	PhpMyAdmin est accessible sur le port défini.
	•	Elasticsearch, Logstash, et Kibana fonctionnent pour collecter et afficher les logs.

Contraintes :
	•	Respectez les bonnes pratiques de sécurité pour chaque service (utilisateur non-root, suppression des privilèges inutiles, etc.).
	•	Assurez-vous que les services démarrent dans le bon ordre.
	•	Implémentez des solutions pour gérer les dépendances, comme des scripts d’attente ou des conditions healthcheck.

Livrables :
	1.	Un fichier docker-compose.yml complet.
	2.	Un fichier .env (avec des exemples de valeurs fictives).
	3.	Les fichiers Docker nécessaires pour PHP-FPM et Nginx.
	4.	Une documentation expliquant :
	•	Les choix techniques effectués.
	•	Les commandes pour démarrer, vérifier et arrêter l’environnement.
	•	Les bonnes pratiques de sécurité appliquées.


