# Data Analyst & Junior Data Engineer

Passionné par la donnée, j’aide les organisations à collecter, transformer, analyser et valoriser leurs informations pour une meilleure prise de décision.
J’ai travaillé sur des projets en business intelligence, machine learning et data science, data engineering, visualisation, automatisation et analyse spatiale (SIG).

---

## À propos de moi

* Data Analyst & Data Engineer en environnement SQL / Python / R / Cloud
* Spécialiste en BI (Power BI, Qlik Sense), pipelines data & ETL
* Compétences avancées en géodonnées : Google Earth Engine, R (sf, raster), QGIS
* Expérience en machine learning : fraude bancaire, classification, clustering
* Conception de workflows data, dashboards opérationnels et automatisation
* Expériences variées : Handicap International, APIM, VAEG JURIDICA, LM ECO Production, Ministère de la Transition Numérique (Mauritanie)
---

# Portfolio – Mes projets


## 1. Analyse des Composants Électriques Aéronautiques – Qlik Sense

## Contexte  
Projet de Business Intelligence réalisé sous **Qlik Sense** pour analyser la gestion des composants électriques d’avions : sécurité, conformité, stocks, délais et qualité des fournisseurs.  
L’objectif est d’aider les équipes (logistique, qualité, achats) à mieux piloter la chaîne d’approvisionnement et à réduire les risques liés aux composants critiques.

---

## Objectif  
Construire un tableau de bord complet permettant de suivre :  
- l’état des stocks (stock de sécurité, stock minimum),  
- les défauts par composant,  
- les délais d’approvisionnement,  
- l’impact économique (prix unitaires, coûts),  
- la performance des fournisseurs.

---

## Approche  
- Compréhension du besoin métier (logistique, qualité, conformité).  
- Modélisation des données :  
  - Dimensions : Dates, Composants, Fournisseurs  
  - Mesures : quantités, délais, défauts, prix  
- Création des KPIs clés dans Qlik Sense :  
  - Stock de sécurité  
  - Taux de défauts par composant  
  - Taux de respect des délais  
  - Prix unitaire par composant  
- Mise en place d’une structure data propre :  
  - Approvisionnement  
  - Relations fournisseurs-composants  
  - Tests réalisés  

---

## Résultats  
- Vision complète de la performance des composants.  
- Identification rapide des composants défectueux et des fournisseurs à risque.  
- Suivi des délais d’approvisionnement pour anticiper les ruptures.  
- Aide à la prise de décision pour la logistique, la qualité et les achats.

---

## Enjeux métiers  
- Sécurité et conformité réglementaire.  
- Gestion des stocks critiques.  
- Optimisation des coûts et des relations fournisseurs.  
- Réduction des retards et interruptions de production.

---

## Visuels du projet  
*(À insérer prochainement)*


Lien du projet : bientôt disponible

---

## 3. Data Lake & Analyse des Offres d’Emploi – Python, Power BI, ETL

## Contexte  
Projet réalisé dans le cadre du Master BI&A (Université Lumière Lyon 2), autour de la création d’un mini Data Lake permettant de collecter, structurer et analyser des données issues de pages web (Glassdoor, LinkedIn).  
Objectif : exploiter ces données pour produire des indicateurs sur le marché de l’emploi IT et les visualiser dans un dashboard Power BI.

---

## Objectif  
Mettre en place un pipeline complet :  
- collecte automatisée de fichiers HTML,  
- gestion des métadonnées techniques et descriptives,  
- création d’un data model (dimensions + table des faits),  
- ETL pour alimenter un entrepôt de données,  
- création d’un dashboard analytique.

---

## Approche  

### 1) Collecte & Métadonnées techniques  
- Déplacement automatisé des fichiers HTML vers la Landing Zone.  
- Génération d’un fichier CSV structuré sous forme de lignes contenant : chemin, source, date, identifiant unique.  
- Architecture en zones : **Landing → Curated → Production**.

### 2) Extraction des métadonnées descriptives  
- Parsing HTML via BeautifulSoup pour extraire :  
  - Offres : libellé, entreprise, ville, pays  
  - Entreprises : taille, secteur  
  - Avis : note, avantages, inconvénients  
- Export vers un CSV structuré en lignes pour une meilleure flexibilité.

### 3) Modèle décisionnel & ETL  
- Modèle en étoile avec 3 dimensions : **Offre**, **Entreprise**, **Avis**.  
- Table des faits construite via Power Query.  
- Indicateurs clés :  
  - Nombre d’offres (par ville, pays, secteur)  
  - Nombre d’entreprises recruteuses  
  - Répartition par taille et secteur

### 4) Visualisation Power BI  
3 pages pour analyser le marché de l’emploi IT :  
- **Vue globale des offres** : carte interactive, secteurs, top entreprises.  
- **Vue entreprises** : taille, secteur, répartition géographique.  
- **Détails entreprise** : note moyenne, avantages/inconvénients, localisation.

---

## Résultats  
- Mise en place d’une chaîne complète de traitement de données semi-structurées.  
- Construction d’un Data Lake fonctionnel (technique + descriptif).  
- Modèle décisionnel exploitable pour la BI.  
- Dashboard interactif pour analyser dynamiquement le marché de l’emploi IT.

---

## Enjeux métiers  
- Comprendre la dynamique de recrutement IT.  
- Identifier les zones géographiques les plus actives.  
- Analyser les secteurs les plus demandeurs.  
- Faciliter la lecture des avis et la perception des entreprises.

---

## Visuels du projet  
*(À insérer prochainement)*

Lien du projet : bientôt disponible

---

## 4. Détection de Fraude Bancaire (Machine Learning)


## Contexte  

Ce projet vise à construire un modèle de Machine Learning capable d’identifier en temps réel les transactions potentiellement frauduleuses. Le dataset, issu d’une grande enseigne française en partenariat avec des institutions bancaires, comporte plus de 6 millions de lignes, dont moins de 1% de fraudes réelles, rendant le problème particulièrement complexe.
Le défi principal : détecter un événement extrêmement rare, sans générer trop de faux positifs qui détérioreraient l’expérience client.
La variable à  prédire est **FlagImpaye** :  
- **0 = Transaction normale**  
- **1 = Transaction frauduleuse**  

Pour cela nous allons améliorer la **F-mesure**, un indicateur adapté aux classes rares.

---

## Approche  
- Préparation des données : nettoyage, encodage, standardisation.  
- Division temporelle du dataset pour simuler un cas réel.  
- Traitement du fort déséquilibre : **SMOTE**, **Tomek Links**, **pondération de classes**.  
- Modèles testés : Logistic Regression, Random Forest, SVM, XGBoost.  
- Optimisation : **GridSearchCV** + ajustement du seuil de prédiction.

---

## Résultats  
- **Sans rééquilibrage** : aucune fraude détectée (Recall = 0%).  
- **Avec SMOTE** : meilleure détection mais trop de faux positifs.  
- **Avec SMOTE + Tomek Links + XGBoost** :  
  - amélioration du Recall,  
  - augmentation du F1-score,  
  - meilleur équilibre entre détection et faux positifs.

---

## Enseignements  
Le projet met en évidence la complexité des problèmes de classes rares, la nécessité d’un prétraitement rigoureux et l’importance du tuning du seuil pour optimiser la performance réelle.

---

## Visuels du projet  
*(à ajouter prochainement)*

(Lien vers le projet disponible prochainement)

## 5. Pixel Wise T-Test (PWTT) – Analyse de changements (Sentinel-1)

**Google Earth Engine · Radar VV/VH · T-test**

Pipeline d’analyse automatisée pour détecter des changements spatiaux via des séries temporelles radar.

* Calcul de t-test pixel par pixel (avant/après)
* Agrégation sur grille régulière
* Export des statistiques en CSV et raster
* Conçu pour des zones complexes nécessitant un monitoring géospatial

Lien du projet : bientôt disponible

---

---

# Compétences techniques

### Langages

Python, SQL, R, DAX, JavaScript (bases)

### Machine Learning

Feature engineering, réduction de déséquilibre, XGBoost, Random Forest, SVM, Logistic Regression

### Data Engineering

Pipelines ETL/ELT, automatisation Python, ingestion API, Spark (bases)

### BI & DataViz

Power BI, Qlik Sense, Tableau, Plotly

### SIG

QGIS, ArcGIS, Google Earth Engine, traitement raster/vectoriel

### Bases de données

PostgreSQL, MySQL, DuckDB, BigQuery

---

# Expériences

* 2024–2025 : Handicap International – Data Analyst & BI/SIG
* 2024 : Handicap International – Mission Data
* 2023 : APIM – Data Marketing & Analyse des agréments
* 2023 : Développeur Full Stack
* 2022 : IT Production

---

# Me contacter

Email : *ajouter votre email*
LinkedIn : *ajouter votre lien*
Portfolio : *moi-meme.github.io*


