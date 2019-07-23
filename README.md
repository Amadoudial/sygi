# sygi
Cette application a été générée à l'aide de JHipster 5.8.2. Vous pouvez trouver de la documentation et de l'aide à l' adresse https://www.jhipster.tech/documentation-archive/v5.8.2 .

Développement
Avant de pouvoir générer ce projet, vous devez installer et configurer les dépendances suivantes sur votre ordinateur:

Node.js : Nous utilisons Node pour exécuter un serveur Web de développement et générer le projet. En fonction de votre système, vous pouvez installer Node à partir de la source ou en tant qu’ensemble pré-packagé.
Après avoir installé Node, vous devriez pouvoir exécuter la commande suivante pour installer les outils de développement. Vous ne devrez exécuter cette commande que lorsque les dépendances changent dans package.json .

npm install
Nous utilisons les scripts npm et Webpack comme système de construction.

Exécutez les commandes suivantes sur deux terminaux distincts pour créer une expérience de développement enrichissante dans laquelle votre navigateur s'actualise automatiquement lorsque les fichiers changent sur votre disque dur.

./mvnw
npm start
Npm est également utilisé pour gérer les dépendances CSS et JavaScript utilisées dans cette application. Vous pouvez mettre à niveau les dépendances en spécifiant une version plus récente dans package.json . Vous pouvez également exécuter npm updateet npm installgérer des dépendances. Ajoutez le helpdrapeau sur n’importe quelle commande pour voir comment vous pouvez l’utiliser. Par exemple, npm help update.

La npm runcommande listera tous les scripts disponibles à exécuter pour ce projet.

Travailleurs de service
Les techniciens du service après-vente sont commentés par défaut. Pour les activer, veuillez supprimer le commentaire suivant.

Le script d’enregistrement du travailleur de service dans index.html
< script >
    if ( ' serviceWorker '  dans le  navigateur ) { 
navigateur . serviceWorker . enregistrer ( ' ./service-worker.js ' ). then ( function () { console . log ( ' Service Worker Registered ' );         });     }        
            


</ script >
Remarque: la boîte de travail crée le prestataire de service concerné et génère dynamiquement le service-worker.js

Gérer les dépendances
Par exemple, pour ajouter la bibliothèque Leaflet en tant que dépendance d'exécution de votre application, vous devez exécuter la commande suivante:

npm install --save --save-exact leaflet
Pour tirer parti des définitions de type TypeScript du référentiel DefinitelyTyped en développement, vous devez exécuter la commande suivante:

npm install --save-dev --save-exact @types/leaflet
Vous devez ensuite importer les fichiers JS et CSS spécifiés dans les instructions d'installation de la bibliothèque afin que Webpack en soit informé: Modifiez le fichier src / main / webapp / app / vendor.ts :

import 'leaflet/dist/leaflet.js';
Editez le fichier src / main / webapp / content / css / vendor.css :

@import '~leaflet/dist/leaflet.css';
Remarque: il ne reste que peu de choses à faire pour Leaflet que nous ne détaillerons pas ici.

Pour plus d'instructions sur la façon de développer avec JHipster, consultez Utilisation de JHipster en développement .

En utilisant angular-cli
Vous pouvez également utiliser Angular CLI pour générer du code client personnalisé.

Par exemple, la commande suivante:

ng generate component my-component
va générer quelques fichiers:

create src/main/webapp/app/my-component/my-component.component.html
create src/main/webapp/app/my-component/my-component.component.ts
update src/main/webapp/app/app.module.ts
Bâtiment de production
Pour optimiser l'application casal pour la production, exécutez:

./mvnw -Pprod clean package
Cela concaténera et réduira les fichiers CSS et JavaScript du client. Il sera également modifié index.htmlafin de référencer ces nouveaux fichiers. Pour que tout fonctionne, exécutez:

java -jar target/*.war
Ensuite, accédez à http: // localhost: 8080 dans votre navigateur.

Reportez-vous à Utilisation de JHipster en production pour plus de détails.

Essai
Pour lancer les tests de votre application, exécutez:

./mvnw clean test
Tests clients
Les tests unitaires sont gérés par Jest et écrits avec Jasmine . Ils sont situés dans src / test / javascript / et peuvent être exécutés avec:

npm test
Pour plus d'informations, reportez-vous à la page Tests en cours .

Qualité du code
Sonar est utilisé pour analyser la qualité du code. Vous pouvez démarrer un serveur Sonar local (accessible sur http: // localhost: 9001 ) avec:

docker-compose -f src/main/docker/sonar.yml up -d
Ensuite, lancez une analyse Sonar:

./mvnw -Pprod clean test sonar:sonar
Pour plus d'informations, reportez-vous à la page Qualité du code .

Utilisation de Docker pour simplifier le développement (facultatif)
Vous pouvez utiliser Docker pour améliorer votre expérience de développement JHipster. Un certain nombre de configurations composées par docker sont disponibles dans le dossier src / main / docker pour lancer les services tiers requis.

Par exemple, pour démarrer une base de données postgresql dans un conteneur docker, exécutez:

docker-compose -f src/main/docker/postgresql.yml up -d
Pour l'arrêter et supprimer le conteneur, exécutez:

docker-compose -f src/main/docker/postgresql.yml down
Vous pouvez également entièrement dockériser votre application et tous les services qui en dépendent. Pour ce faire, commencez par créer une image de menu fixe de votre application en exécutant:

./mvnw package -Pprod verify jib:dockerBuild
Puis lancez:

docker-compose -f src/main/docker/app.yml up -d
Pour plus d'informations, voir Utilisation de Docker et Docker-Compose , cette page contient également des informations sur le sous-générateur de docker-composition ( jhipster docker-compose), capable de générer des configurations de menu fixe pour une ou plusieurs applications JHipster.

Intégration continue (facultatif)
Pour configurer le CI pour votre projet, exécutez le sous-générateur ci-cd ( jhipster ci-cd), cela vous permettra de générer des fichiers de configuration pour un certain nombre de systèmes à intégration continue. Consultez la page Configuration de l'intégration continue pour plus d'informations.
