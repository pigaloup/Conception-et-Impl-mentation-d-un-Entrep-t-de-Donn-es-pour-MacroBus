## 🏗️ Conception et Implémentation d'un Entrepôt de Données pour MacroBus

Description du projet : MacroBus, une entreprise spécialisée dans la vente de véhicules sur plusieurs marchés, souhaite optimiser ses performances commerciales et faciliter la prise de décision à travers un système dédié. Pour ce faire nous devons mettre en place un entrepôt de données pour servir de source aux tableaux de bord décisionnels afin de piloter efficacement l’activité commerciale et analyser les commandes. 
Parties Prenantes : PDG, Gestionnaire de base de données, Data Engineering, Data Analyst.

Objectif Général : L'objectif principal est de transformer des données transactionnelles brutes en une source de données 
structurée et fiable pour piloter la performance commerciale via des tableaux de bord décisionnels .

## 🎬 [Télécharger la vidéo de démonstration](https://github.com/pigaloup/Conception-et-Impl-mentation-d-un-Entrep-t-de-Donn-es-pour-MacroBus/blob/main/Doc/MacroBus.mp4)

-----

# 🎯 Objectifs du Projet

* Centralisation : Créer un entrepôt de données (Data Warehouse) robuste et fiable.
* Modélisation : Structurer les données via une **modélisation en étoile**.
* Chargement : Automatiser le **chargement des données** avec SQL et Talend.
* Qualité : Garantir l'intégrité des données via des tests de validation fonctionnelle rigoureux.
* Aide à la Décision : Fournir une source de données unique et fiable pour le PDG et les analystes.
* Analyse Performance : Piloter l'activité commerciale (ventes par territoire, top commerciaux, catégories produits) dans Power Bi.

-----
# 🛠️ Stack Technique

* Stockage : MySQL (Base source et Data Warehouse).
* ETL / Intégration : Talend Open Studio & Scripts SQL.
* Modélisation : Star Schema (Schéma en étoile).
* Data Visualisation : Power BI.
* Langages : SQL
* Outils de Gestion : MySQL Workbench.
* 
-----

# 📐 Architecture & Étapes Clés

Le projet suit une architecture de modélisation dimensionnelle en étoile pour optimiser les performances de lecture et simplifier les analyses croisées.

# 1. Restauration et Préparation (ETL)
Extraction des données sources et conversion en format .csv pour optimiser le chargement.
Nettoyage et structuration initiale sous MySQL Workbench.

# 2. Modélisation en étoile
Conception d'un schéma en étoile pour maximiser les performances de lecture.

![Modélisation en étoile](https://github.com/pigaloup/Conception-et-Impl-mentation-d-un-Entrep-t-de-Donn-es-pour-MacroBus/blob/main/image/modelisation%20en%20%C3%A9toile.PNG)

  **Table de Faits** : fact_orderdetails (Commandes, montants et clés étrangères).
  **Dimensions** :
              - dim_customers : Segmentation géographique et client.
              - dim_products  : Catalogue et catégories de véhicules.
              - dim_employees : Hiérarchie et performance des commerciaux.
              - dim_calendar  : Granularité temporelle (Année, Semestre, Trimestre, Mois, Jour).

3. **Création de l’entrepôt de données**  
   - Scripts SQL pour générer les tables de dimensions et de faits.  

4. **Chargement des données**  
   - Via scripts SQL.  
   - Via jobs Talend (Développement de jobs ETL complexes utilisant le composant tMap pour le mapping, le filtrage et la transformation des données vers les tables cibles).
     
![Tmap](https://github.com/pigaloup/Conception-et-Impl-mentation-d-un-Entrep-t-de-Donn-es-pour-MacroBus/blob/main/image/tmapfait.PNG)

![Table de fait](https://github.com/pigaloup/Conception-et-Impl-mentation-d-un-Entrep-t-de-Donn-es-pour-MacroBus/blob/main/image/TABLEDEFAIT.PNG)

-----

# 🛡️ Validation & Qualité des Données (Data Quality)
La fiabilité étant critique, j'ai instauré un protocole de validation comparant les résultats entre la source et le Data Warehouse (via SQL et Talend).

Pour ce faire, j'ai mis en place d'une phase de tests rigoureuse pour garantir l'intégrité des données (Data Quality) en comparant les résultats entre la source, le chargement par 
script SQL et le flux Talend :


| Indicateur de Test         | Source Brute | DWH (SQL/Talend) | Statut    |
|----------------------------|--------------| -----------------|-----------|
| Nombre de lignes chargées  | 2996         | 2996             | ✅ OK     |
| Montant total des ventes   | 9 604 536    | 9 604 149        | ✅ Validé |
| Volume de commandes        | 326          | 326              | ✅ OK     |
| Ventes S2 2003             | 2 395 971    | 2 395 971        | ✅ OK     |

*Note : Les écarts mineurs constatés ont été analysés et validés comme conformes aux règles de gestion des arrondis lors de la transformation.

-----

# 📊 Business Insights (Power BI)
Le système permet de répondre instantanément à des questions métiers complexes :

[👉 Voir la Visualisation des données dans Power BI](https://github.com/pigaloup/Conception-et-Impl-mentation-d-un-Entrep-t-de-Donn-es-pour-MacroBus/blob/main/Doc/Projet1_MacroBus.pbix).

1. **Top Territoires** : Les USA dominent avec plus de 3,2M de montant total.
![Visualisation des données1](ETL+AIRFLOW/1.PNG)

3. **Productivité** : Identification du Top 3 des commerciaux (ex: Gerard Hernandez avec 43 commandes).
![Visualisation des données2](ETL+AIRFLOW/2.PNG).

5. **Analyse Produit** : Les "Classic Cars" représentent plus de 52% du volume commandé au T2 2003.
![Visualisation des données2](ETL+AIRFLOW/2.PNG).

## 🌟 Compétences Démontrées
- Conception et implémentation d’un **entrepôt de données**.  
- **ETL et intégration de données** avec Talend.  
- **Modélisation dimensionnelle** (schéma en étoile).  
- **SQL avancé** (jointures, agrégations, transformations).  
- **Validation et assurance qualité des données**.  
- **Business Intelligence** avec Power BI.  

## 🎬 [Télécharger la vidéo de démonstration](https://github.com/pigaloup/Conception-et-Impl-mentation-d-un-Entrep-t-de-Donn-es-pour-MacroBus/blob/main/Doc/MacroBus.mp4)

-----

## 🚀 Conclusion et recommandation

**Conclusions** : Le projet optimise les performances commerciales de l’entreprise MacroBus et faciliter la prise de décision à travers un système dédié

**Recommandations** : la solution pourrait être étendue avec des modèles prédictifs (Machine Learning) basés sur l'historique des commandes pour anticiper les stocks et les tendances de ventes futures.

Exemple : Les modèles prédictifs basés sur le machine learning

-----

## 🚀 Objectif Professionnel
Ce projet illustre ma capacité à **transformer des données brutes en informations stratégiques**.  
Mon ambition est de contribuer en tant que **Data Engineer** à la mise en place de solutions analytiques performantes pour soutenir la prise de décision dans des environnements complexes.

---

## 📌 Auteur

👤 **El Hadji Ablaye Galoup Diop**  

  - Data Engineering | Data Analysis | BI
  - Expérience en gestion de production, inventaire et optimisation des processus.  
  - Certifications : IBM Data Warehouse Engineer, intelligence artificielle, Data Analysis.  

---
