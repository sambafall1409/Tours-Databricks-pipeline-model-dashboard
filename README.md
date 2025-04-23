# 🏗️ Tours Databricks Pipeline & ML Dashboard

## 📌 Contexte
Ce projet traite les mutations immobilières via un pipeline Databricks, allant de la **bronze** à la **gold**, suivi d’un **modèle de machine learning** prédictif pour estimer les prix au m². Le tout est orchestré et automatisé via des **workflows Databricks**.

---

## ⚙️ Architecture du Pipeline

- 🔸 **Bronze** : ingestion brute (fichier mutation.csv)
- 🔹 **Silver** : nettoyage, typage et enrichissement
- 🟡 **Gold** : table de faits + dimensions (bien, localisation, nature, date)

---

## 🤖 Machine Learning

- 🎯 Objectif : prédire le **prix au m²**
- 🔍 Algorithmes testés :
  - Régression Linéaire
  - Random Forest
- 📊 Meilleur modèle : Random Forest avec **R² ≈ 0.48**

---

## 🔁 Automatisation

Deux workflows Databricks :

1. **ETL Workflow**
   - Fréquence : quotidienne
   - Rôle : mise à jour des données de la silver à la gold

2. **ML Workflow**
   - Fréquence : tous les 3 jours
   - Rôle : réentraînement automatique du modèle sur les dernières données

---

## 🧪 Suivi & Logs

- 📁 Résultats stockés dans le dossier `dvfgold`
- 📝 Logs d'entraînement conservés (RMSE, R², importance des variables)
- 🔢 Sélection automatique du meilleur modèle selon RMSE

---

