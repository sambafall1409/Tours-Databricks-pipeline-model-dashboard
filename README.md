# 🏗️ Tours Databricks Pipeline & ML Dashboard

## 📌 Contexte
Ce projet traite les mutations immobilières via un pipeline **Databricks**, allant de la **bronze** à la **gold**, suivi d’un **modèle de machine learning** prédictif pour estimer les **prix au m²**. L’ensemble est **automatisé via des workflows Databricks** et **connecté à Power BI** pour l’analyse des KPIs métiers.

---

## ⚙️ Architecture du Pipeline

- 🔸 **Bronze** : ingestion brute depuis **Azure SQL Database** et **sources locales**
- 🔹 **Silver** : nettoyage, typage, enrichissement des données
- 🟡 **Gold** : modélisation en **étoile** avec une table de faits et plusieurs dimensions :
  - bien
  - localisation
  - nature de mutation
  - date

---

## 📊 Visualisation des KPIs

Les données **gold** alimentent un **dashboard Power BI** connecté, permettant de suivre :
- L'évolution des **valeurs foncières par commune**
- Les **prix au m² par type de bien**
- La **répartition temporelle et géographique**
- L’impact du **type d’acquéreur** et de la **nature de mutation**

---

## 🤖 Machine Learning

- 🎯 Objectif : expliquer les facteurs influençant le **prix au m²**
- 🧠 Algorithmes testés :
  - Régression Linéaire
  - Random Forest (meilleur score)

> 📌 **NB :** Le modèle est **expliquant, non prédictif**. Son but est de **valider les hypothèses métiers** :
> - 🏘️ La **localisation** (code INSEE) est **le facteur le plus déterminant**
> - 👥 Le **type d’acheteur** (rolea)
> - 📦 La **nature de mutation**
> - 📅 Le **mois de mutation**

- 📊 **Performance du meilleur modèle :**
  - RMSE ≈ **749**
  - R² ≈ **0.48**
  - Feature importance montrant une **prédominance géographique forte**

---

## 🔁 Automatisation (Workflows Databricks)

1. **ETL Workflow**  
   - ⏱️ Fréquence : quotidienne  
   - 🛠️ Rôle : alimentation des couches silver & gold

2. **ML Workflow**  
   - ⏱️ Fréquence : tous les 3 jours  
   - 🧠 Rôle : réentraînement automatique du modèle ML

---

## 🧪 Suivi & Logs

- 📁 Données de sortie dans : `/dvfgold`
- 📌 **Historique complet** :
  - RMSE / R²
  - Importance des features
- ✅ Sélection automatique du meilleur modèle via comparaison multi-algorithmes

---

## 🚀 Lancer localement

```bash
git clone https://github.com/sambafall1409/Tours-Databricks-pipeline-model-dashboard.git
