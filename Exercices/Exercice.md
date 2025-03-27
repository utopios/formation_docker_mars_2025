### Exercice1 : Déployer une application PHP

**Objectif** : Déployer une application PHP simple dans un conteneur Docker. Vous utiliserez uniquement des commandes Docker pour configurer et exécuter le conteneur.

- Préparer le fichier PHP
    - Créez un répertoire local pour l’application :

    - Créez un fichier index.php dans ce répertoire avec le contenu suivant :

```php
<?php
Hello, Docker (No Dockerfile)!"; 
echo "
This is a PHP application running in a container.

"; 
?>
```

- Lancer un conteneur PHP
    - Utilisez l’image officielle PHP avec Apache et copier le fichier dans le conteneur.

- Interagir avec le conteneur