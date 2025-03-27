
### 🧪 Exercice 2 : Créer une image Docker qui exécute une tâche cron toutes les minutes

⸻

🎯 **Objectif pédagogique**
- Créer un Dockerfile basé sur Debian ou Ubuntu
- Installer et configurer cron
- Automatiser l’exécution d’un script
- Comprendre le fonctionnement des processus en foreground dans un conteneur
- Travailler avec COPY, RUN, CMD, ENTRYPOINT

⸻

**📜 Contexte**

On vous demande de créer un conteneur Docker qui exécute un script toutes les minutes, par exemple un script qui écrit la date dans un fichier log.

⸻

📝 Structure du dossier docker-cron/

```docker-cron/
├── Dockerfile
├── cronjob
└── scripts/
    └── log-date.sh
```




🔧 Contenu des fichiers

scripts/log-date.sh

```
#!/bin/bash
echo "Date actuelle : $(date)" >> /var/log/cron.log
```

N'oubliez pas de rendre le script exécutable : chmod +x scripts/log-date.sh



**cronjob**

``* * * * * /scripts/log-date.sh``


1. Créez le dockerfile
2. Tesez le dockerfile