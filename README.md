# 🏗️ Tours Databricks Pipeline & ML Dashboard

## 📌 Contexte
Ce travail les mutations immobilières via un pipeline Databricks, allant de la **bronze** à la **gold**, suivi d’un **modèle de machine learning** prédictif pour estimer les **prix au m²**. Le tout est orchestré et automatisé via des **workflows Databricks**.

---

## ⚙️ Architecture du Pipeline

- 🔸 **Bronze** : ingestion brute des données depuis **Azure SQL Database** et sources locales 
- 🔹 **Silver** : nettoyage, typage, enrichissement (calculs, filtrage…)
- 🟡 **Gold** : construction de la **table de faits** et des **dimensions** :
  - bien
  - localisation
  - nature de mutation
  - date

---

## 📊 Visualisation des KPIs

Les données gold sont **connectées à Power BI** afin de visualiser les indicateurs métiers :
- Valeur foncière moyenne par commune
- Prix au m² par type de bien
- Comparaison inter-annuelle
- Evolution géographique

---

## 🤖 Machine Learning

- 🎯 Objectif : prédire le **prix au m²**
- 🔍 Algorithmes testés :
  - Régression Linéaire
  - Random Forest
- 📊 Meilleur modèle : **Random Forest** avec **R² ≈ 0.48**

---

## 🔁 Automatisation

Deux **workflows Databricks** orchestrent le projet :

1. **ETL Workflow**
   - Fréquence : quotidienne
   - Objectif : charger les nouvelles données et mettre à jour les tables gold

2. **ML Workflow**
   - Fréquence : tous les 3 jours
   - Objectif : réentraîner automatiquement le modèle sur les dernières données disponibles

---

## 🧪 Suivi & Logs

- 📁 Résultats stockés dans le dossier `dvfgold`
- 📝 Historique des logs d'entraînement (RMSE, R², importance des features)
- 🔢 Sélection automatique du **meilleur modèle** (basé sur le RMSE)

---

## 🚀 Lancer localement

```bash
git clone https://github.com/sambafall1409/Tours-Databricks-pipeline-model-dashboard.git

