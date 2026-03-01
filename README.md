# 📊 Power BI Dashboard : Analyse Commerciale Mondiale

## 📝 Présentation du Projet
Ce projet Power BI est une solution de **Business Intelligence** complète conçue pour analyser les performances d'une entreprise de distribution opérant sur **22 marchés internationaux**. 

L'objectif est de croiser les flux transactionnels (ventes) avec un référentiel client mondial, un catalogue de produits structuré et des données logistiques pour extraire des insights stratégiques.

---

## 📂 Sources de Données

### 1. Référentiel Clients (Consolidé)
Le projet intègre des données clients provenant de 22 pays (Europe, Amérique du Nord et du Sud) :
* **Pays inclus :** Allemagne, Angleterre, Argentine, Autriche, Belgique, Brésil, Canada, Danemark, Espagne, États-Unis, Finlande, France, Irlande, Italie, Mexique, Norvège, Pologne, Portugal, Suède, Suisse, Venezuela.
* **Données clés :** `Code Client`, `Nom`, `Ville`, `Pays`, `Coordonnées`.

### 2. Catalogue Produits
* **Articles :** Détails des produits, prix de vente, prix de revient et niveaux de stock.
* **Familles :** Catégorisation des produits (Vêtements Hommes/Femmes, Chaussures, Bébé, etc.).

### 3. Opérations
* **Commandes :** Historique des transactions (Dates, Quantités, Remises, Prix unitaires).
* **Transporteurs :** Liste des prestataires logistiques (Transport Express, Allo Express World, etc.).

---

## 🏗️ Architecture du Modèle (Schéma en Étoile)
Pour garantir une performance optimale et une flexibilité de filtrage, le modèle suit une structure en **Star Schema** :

* **Table de Faits :** * `Commandes`
* **Tables de Dimensions :**
    * `Clients` (liée par `Code Client`)
    * `Articles` (liée par `Code Article`)
    * `Transporteurs` (liée par `Code Transporteur`)
    * `Familles` (liée à `Articles` par `Code Famille`)

---

## 🚀 Indicateurs de Performance (KPIs)
Le tableau de bord permet de piloter quatre axes majeurs :

* **Analyse Financière :** Chiffre d'Affaires (CA) total, Marge brute, et analyse de l'impact des remises sur la rentabilité.
* **Analyse Géographique :** Performance par Pays et par Ville via des visualisations cartographiques.
* **Analyse Produits :** Classement (Top 10) des articles et performance par catégorie (Famille).
* **Logistique :** Répartition du volume d'expédition et performance par transporteur.

---

## 🛠️ Instructions Techniques & Transformation (ETL)
1. **Fusion des pays :** Dans *Power Query*, utiliser la fonction "Combiner les fichiers" sur le répertoire contenant les 22 fichiers CSV/Excel pays pour générer une table `Clients` unique.
2. **Nettoyage :** * Assurer le typage de la colonne `Date de Cde` en format **Date**.
    * Convertir les colonnes monétaires en **Nombre décimal fixe**.
3. **Design :** Application du template `PowerBI_application.pbit` pour assurer une cohérence visuelle et le respect des normes d'accessibilité.

---
> **Note :** Projet réalisé dans le cadre de l'analyse de données Power BI - 2025.
