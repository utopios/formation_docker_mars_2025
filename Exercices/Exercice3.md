
🧪 Exercice : Utilisation d’un réseau bridge personnalisé dans Docker

🎯 Objectif pédagogique :

Permettre aux apprenants de comprendre comment créer un réseau Docker personnalisé de type bridge et comment il permet la communication entre conteneurs par leurs noms.



Étape 1 : Création d’un réseau personnalisé

Créez un réseau Docker personnalisé utilisant le pilote bridge. Donnez-lui un nom explicite, par exemple lié à une application.

Étape 2 : Lancement de deux conteneurs dans ce réseau

Lancez deux conteneurs légers (par exemple basés sur Alpine ou BusyBox) et connectez-les directement au réseau que vous avez créé. Nommez-les service1 et service2.

Étape 3 : Test de communication entre les conteneurs

Depuis le conteneur service1, essayez de communiquer avec service2 en utilisant son nom. Observez si la communication fonctionne (ex. : via un ping ou une requête simple).

Étape 4 : Inspection du réseau

Observez le réseau personnalisé que vous avez créé. Notez :
	•	les adresses IP attribuées,
	•	la présence des conteneurs connectés,
	•	et le fait que la résolution DNS fonctionne dans ce réseau.



