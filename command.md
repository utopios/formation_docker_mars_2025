### Démarrer un conteneur : 

```docker run <option> <nom_image> ```

**Options :**

- `-d` : détaché
- `--name`: nom du conteneur
- `-it`: shell interactif

### Liste des conteneurs :

- ```docker ps ``` *avec l'option `-a` pour voir la totalité (en arrêt et démarrés)* 
- ```podman ps ```

### Supprimer un conteneur:

- `docker rm <id ou nom_conteneur>`
- `podman rm <id ou nom_conteneur>`

### Envoyer une commande à un conteneur:

- `docker exec <option> <nom ou id conteneur> <commande>`
- `podman exec <option> <nom ou id conteneur> <commande>`

### Copier des ressources dans un conteneur:

- `docker cp <path_fichier> <nom ou id conteneur>:<path_destination_fichier>`