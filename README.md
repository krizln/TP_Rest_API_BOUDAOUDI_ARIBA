# TP_Dev_Web_BOUDAOUDI_ARIBA
# I- Initialisation du projet et première route
1. Initialisation et Configuration

Le projet a été initialisé avec npm init -y et les dépendances clés (express, sqlite3, cors) ont été installées. Nodemon a été ajouté pour le développement afin d'assurer le rechargement automatique. Un fichier .gitignore a été configuré pour exclure les node_modules, les fichiers .db et .env, garantissant ainsi un dépôt de code propre.

2. Création du Serveur Express

Le fichier index.js a été créé pour servir de point d'entrée. L'application Express a été instanciée et configurée avec les middlewares essentiels : cors() pour autoriser les requêtes externes et express.json() pour parser le corps des requêtes JSON. Une route GET sur / a permis de valider le bon lancement du serveur via npm run dev : 

<img width="389" height="96" alt="image" src="https://github.com/user-attachments/assets/b9aa657e-0770-4055-b925-6677a986c670" />


3. Définition des Routes CRUD

Le squelette de l'API RESTful a été défini pour la ressource /api/cars. Les routes pour les opérations CRUD (Create, Read, Update, Delete) ont été implémentées : GET (pour lister et récupérer par ID), POST (création), PUT (modification) et DELETE (suppression). Cela a permis de mettre en place la gestion des paramètres d'URL (req.params) et du corps de la requête (req.body).

4. Validation avec Postman

Tous les endpoints ont été testés à l'aide de Postman. Cet outil a été indispensable pour simuler des requêtes autres que GET. Le test de la route POST, en envoyant un corps JSON, a confirmé que le serveur recevait et comprenait correctement les données. L'ensemble des routes a fonctionné comme attendu, validant l'architecture de l'API avant la connexion à la base de données.

-> GET toutes les voitures : 

<img width="638" height="106" alt="image" src="https://github.com/user-attachments/assets/7fa36cf8-6da7-4b41-ab32-b23d4a23325e" />

-> GET une voiture spécifique :

<img width="254" height="64" alt="image" src="https://github.com/user-attachments/assets/369e6779-adf8-479c-a7fe-3ad6182d8363" />

-> POST créer une voiture :

<img width="299" height="153" alt="image" src="https://github.com/user-attachments/assets/3a87140b-be92-4497-a065-7b67c8d22c2b" />


# II- Base de données SQLite

5. Mise en place de la base de données

L'intégration de SQLite a été réalisée via la création du module database.js. Ce script gère la connexion au fichier cars.db et automatise la création de la table cars avec son schéma (ID, marque, modèle, etc.) si celle-ci n'existe pas encore. L'importation de ce module dans le point d'entrée index.js permet d'initialiser la base de données dès le démarrage du serveur, assurant ainsi la persistance des données pour les étapes suivantes.


<img width="286" height="41" alt="image" src="https://github.com/user-attachments/assets/4979d261-00c4-4bda-bb01-c511e935e6f5" />

6. Finalisation du peuplement et validation

L’exécution réussie de la commande npm run seed a marqué la finalisation de la couche de persistance du projet. Après avoir résolu l'erreur de référence dans le script seed.js, la connexion à SQLite a été établie avec succès, permettant le vidage de la table et l’insertion de trois enregistrements complets. Ce succès confirme que la communication entre Node.js et SQLite est parfaitement fonctionnelle et que l'API dispose désormais d'un jeu de données réel pour les tests de consultation.

7. Dynamisation des routes et interconnexion de la base de données

Le fichier index.js a été intégralement mis à jour pour assurer la liaison entre le serveur Express et la base de données SQLite. L'implémentation des méthodes db.all et db.get a permis de transformer les routes de consultation en points d'accès dynamiques, capables d'extraire et de filtrer les données réelles stockées dans le fichier cars.db. Cette étape a également permis de valider la gestion des erreurs HTTP, notamment avec le renvoi d'un code d'état 404 en cas de ressource introuvable, garantissant ainsi la robustesse et la conformité de l'API REST aux standards de développement.

Test avec Postman :
- GET http://localhost:3000/api/cars :   

<img width="806" height="571" alt="image" src="https://github.com/user-attachments/assets/0405167d-aadd-4dba-852b-40fbc21e8c42" />


- GET http://localhost:3000/api/cars/1 :

<img width="809" height="349" alt="image" src="https://github.com/user-attachments/assets/f46ce1bb-5f14-47a0-a225-c9d8c1d3a4fc" />


- GET http://localhost:3000/api/cars/999 :

<img width="818" height="183" alt="image" src="https://github.com/user-attachments/assets/c76261b4-6adb-4a2b-9c8e-c778aef8bcb9" />



