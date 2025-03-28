
🧪 Sujet d’exercice – Docker : Gérer la persistance des données avec les volumes

🎯 Objectif :

Mettre en place un volume Docker pour persister des données indépendamment du cycle de vie des conteneurs.

⸻

	1.	Créer un volume Docker nommé data_webapp.
	2.	Lancer un conteneur web (ex. : basé sur Nginx ou httpd) en utilisant ce volume pour stocker ses fichiers de configuration ou ses données web.
	3.	À l’intérieur du conteneur, créer ou modifier un fichier dans le répertoire lié au volume.
	4.	Supprimer le conteneur.
	5.	Recréer un nouveau conteneur en réutilisant le même volume.
	6.	Vérifier que les données précédemment ajoutées sont toujours présentes.
	7.	Inspecter le volume Docker, en identifiant notamment où il est physiquement stocké sur l’hôte.

