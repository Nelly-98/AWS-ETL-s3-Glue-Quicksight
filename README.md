# projet de Data Engineering sur AWS utilisant s3 pour le stockage, Glue pour la transformation et QuickSight pour la visualisation

Ce projet a pour objectif de mettre en œuvre un pipeline de données sur AWS, depuis l'ingestion des données jusqu'à la visualisation des données transformées. Nous utilisons les services AWS suivants :
- AWS S3
- AWS Glue
- AWS QuickSight

## <p align="center"> Architecture du projet</p>

![alt text](https://github.com/Nelly-98/AWS-ETL-s3-Glue-Quicksight/blob/main/etl_glue.png)


## <p align="center"> Collecte des données</p>

Téléchargez le jeu de données de ventes fictif à partir de ce lien : https://www.kaggle.com/kyanyoga/sample-sales-data.

## <p align="center">AWS S3</p>
  
AWS S3 est utilisé pour le stockage des données brutes et transformées. Nous créons deux buckets S3 :
- Bucket source : Pour charger le fichier source CSV.
- Bucket de destination : Pour sauvegarder les données après transformation dans Glue.


## <p align="center">AWS Glue</p>
  
Voici les étapes principales de notre flux de travail Glue :
### 1. Allez dans le service AWS Glue.
- Cliquez sur "Crawlers" dans le panneau de gauche.
- Cliquez sur "Add crawler" pour créer un nouveau crawler.
- Donnez un nom à votre crawler (par exemple, "sales-data-crawler").
- Sélectionnez votre bucket S3 comme source de données.
- Suivez les étapes pour terminer la configuration du crawler.
- Exécutez le crawler pour découvrir et cataloguer les données.
### 2. Création d'un job Glue pour la transformation des données :
- Allez dans le service AWS Glue.
- Cliquez sur "Jobs" dans le panneau de gauche.
- Cliquez sur "Add job" pour créer un nouveau job.
- Donnez un nom à votre job : "sales-data-transformation".
- Sélectionnez le type de script (Python, Scala, ou Spark).
- Utilisez le schéma découvert par le crawler pour écrire un script de transformation.
- Exécutez le job pour transformer les données et les charger dans un nouvel emplacement S3.


## <p align="center">AWS QuickSight</p>

- Connexion aux données : Nous nous connectons au bucket S3 où les données transformées sont stockées à l'aide de QuickSight.
- Création d'un DataSet : Nous créons un DataSet QuickSight en spécifiant le format et la structure des données.
- Création de visualisations : À l'aide du DataSet, nous créons des visualisations telles que des graphiques, des tableaux croisés dynamiques, etc., pour analyser les données.
- Création de tableaux de bord : Nous utilisons ces visualisations pour créer des tableaux de bord interactifs qui fournissent un aperçu complet des données transformées.

![alt text](https://github.com/Nelly-98/AWS-ETL-s3-Glue-Quicksight/blob/main/visualisation.png)

Ce README est conçu pour fournir une base sur laquelle vous pouvez construire. Selon la complexité et les besoins spécifiques de votre projet, vous pourriez vouloir ajouter plus de détails sur la configuration, l'utilisation des secrets, la sécurité, et d'autres meilleures pratiques.



