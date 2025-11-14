# TP_Dev_Web_BOUDAOUDI_ARIBA
1. Initialisation et Configuration

Le projet a été initialisé avec npm init -y et les dépendances clés (express, sqlite3, cors) ont été installées. Nodemon a été ajouté pour le développement afin d'assurer le rechargement automatique. Un fichier .gitignore a été configuré pour exclure les node_modules, les fichiers .db et .env, garantissant ainsi un dépôt de code propre.

2. Création du Serveur Express

Le fichier index.js a été créé pour servir de point d'entrée. L'application Express a été instanciée et configurée avec les middlewares essentiels : cors() pour autoriser les requêtes externes et express.json() pour parser le corps des requêtes JSON. Une route GET sur / a permis de valider le bon lancement du serveur via npm run dev.

3. Définition des Routes CRUD

Le squelette de l'API RESTful a été défini pour la ressource /api/cars. Les routes pour les opérations CRUD (Create, Read, Update, Delete) ont été implémentées : GET (pour lister et récupérer par ID), POST (création), PUT (modification) et DELETE (suppression). Cela a permis de mettre en place la gestion des paramètres d'URL (req.params) et du corps de la requête (req.body).

4. Validation avec Postman

Tous les endpoints ont été testés à l'aide de Postman. Cet outil a été indispensable pour simuler des requêtes autres que GET. Le test de la route POST, en envoyant un corps JSON, a confirmé que le serveur recevait et comprenait correctement les données. L'ensemble des routes a fonctionné comme attendu, validant l'architecture de l'API avant la connexion à la base de données.
