### Démarrer un conteneur : 

```docker run <option> <nom_image> ```

**Options :**

- `-d` : détaché
- `--name`: nom du conteneur
- `-it`: shell interactif
- `-p`: mappage des ports

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

### Créer une image à partir d'un conteneur:

- `docker commit <id_ou_nom_conteneur> <adresse/nom_image:tag>`

### Créer une image à partir d'un dockerfile:

- `docker build -t <nom_image> <context_execution>`

### Lister les réseaux sur docker

- `docker network ls`

### Connecter un conteneur à un réseau:

- `docker network connect <reseau> <conteneur>`