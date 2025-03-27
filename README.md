# Modélisation de la satisfaction urbaine et environnement vert

Ce projet vise à modéliser la satisfaction des habitants en fonction de l’environnement végétal urbain à partir de données suisses issues du Swiss Household Panel (SHP) et d’indicateurs spatiaux de couverture végétale. L’objectif est de produire un modèle de classification permettant d’identifier les conditions environnementales associées à une plus grande satisfaction des résidents, avec une application possible sur d’autres territoires comme la ville de Montélimar.

🔍 Ce dépôt contient le code complet de :

La lecture et la fusion des données d’enquête et environnementales

Le nettoyage des variables et la création de la cible

La modélisation avec XGBoost

Les courbes ROC/PR, les matrices de confusion, et l’évaluation finale

⚠️ Données non incluses

Les données utilisées sont issues de deux fichiers confidentiels :

shp21_p_user.dta et shp21_h_user.dta: Enquête Swiss Household Panel, vague 2021


Ces fichiers ne sont pas distribués dans ce dépôt pour des raisons de confidentialité. Vous pourrez également retrouvé une documentation détaillant les champs dans les données attribues par le FORS

📥 Obtenir les données

Créer un compte sur le portail FORSbase : https://forsbase.unil.ch/

Rechercher le projet “Swiss Household Panel (SHP)” – Vague 2021

Faire une demande d’accès aux fichiers de données utilisateurs restreints

Une fois l'accès approuvé, télécharger :

Le fichier .dta contenant les données individuelles et ménages

🧠 Structure du code (extrait principal)

Importation des fichiers .dta et .csv via pandas

Fusion des deux jeux de données sur la clé commune idhous21

Nettoyage des colonnes et filtrage sur la zone 210m uniquement

Binarisation de la variable de satisfaction (p21c44 ≥ 8 → 1, sinon 0)

Séparation des données en train/test

Entraînement d’un modèle XGBoost

Application d’un RandomOverSampler pour équilibrer les classes

Évaluation via ROC AUC, PR AUC, matrice de confusion et classification report

Sauvegarde des figures au format PNG

📦 Dépendances

Assurez-vous d’avoir les librairies suivantes installées :

pandas

numpy

matplotlib

seaborn

scikit-learn

imblearn

xgboost

pyreadstat (pour lire les fichiers .dta)

jupyter (optionnel pour explorations)

📁 Exemple de structure de fichiers attendue

│
├── script_principal.py
├── data/
│ ├── shp21_p_user.dta
│ └── greenery_land_usage_data.csv
├── figures/
│ ├── ROC.png
│ └── MatriceConfusion.png
└── README.md

📩 Pour toute question

Ce projet a été réalisé dans le cadre du Master 2 Probabilités et Statistiques des Nouvelles Données – Université Gustave Eiffel, en collaboration avec Ecolab (Ministère de la Transition écologique).

—
