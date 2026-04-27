# TODO — Projet AI/ML Smart School (Partie 1 : Failure Prediction)

## Objectif

Construire un modèle de Machine Learning capable de prédire la note d’un étudiant à un examen.

Le but métier est :
- si la note prédite < 50 → l’école propose un soutien supplémentaire

Donc :
- problème de régression (prédiction de note)
- avec interprétation métier possible en classification secondaire (<50 / >=50)

Dans cette todo list, les points 1 à 6 concernent d'abord le traitement de données. Puis on s'attaquera à un premier modèle de base au point 7. Et ensuite on s'occupera de faire notre IA personnel dans les points suivants.

---

# PLAN GLOBAL

- [ ] Récupérer le dataset
- [ ] Faire une EDA sérieuse
- [ ] Préparer les données correctement
- [ ] Sélectionner / créer les bonnes features
- [ ] Tester plusieurs modèles
- [ ] Comparer les performances
- [ ] Faire du tuning d’hyperparamètres
- [ ] Analyser overfitting / underfitting
- [ ] Construire baseline de comparaison
- [ ] Produire graphiques + interprétation critique
- [ ] Rédiger le rapport

---

# 1. Dataset

## Structure générale

- [ ] Charger le dataset
- [ ] Identifier :
  - [ ] nombre de lignes
  - [ ] nombre de colonnes
  - [ ] variables potentiellement inutiles (ID, doublons, etc.)
- [ ] variable cible = grade final
- [ ] Vérifier :
  - [ ] `.head()`
  - [ ] `.info()`
  - [ ] `.describe()`
  - [ ] `.describe(include='all')`
---

# 2. Exploratory Data Analysis (EDA)

## Analyse de la target (grade final)

Ce serait intéressant de faire des graphs montrant la situation des étudiants au début du rapport.

- [ ] Distribution des notes
- [ ] Histogramme
- [ ] Boxplot
- [ ] Moyenne / médiane / variance
- [ ] Vérifier déséquilibre :
  - [ ] beaucoup de fails ?
  - [ ] beaucoup de notes élevées ?

## Analyse univariée

Pour chaque feature importante :

- [ ] regarder la distribution
- [ ] valeurs extrêmes
- [ ] skewness éventuelle


## Analyse bivariée

Relation feature → target

- [ ] corrélations numériques
- [ ] heatmap de corrélation
- [ ] scatterplots importants
- [ ] boxplots pour variables catégorielles

Exemple :
- [ ] study time vs grade

## Analyse multivariée

- [ ] interactions potentielles entre features
- [ ] patterns cachés
- [ ] groupes d’étudiants similaires

---

# 3. Analyse d’importance des Features

## Importance logique

- [ ] Identifier intuitivement les variables importantes

## Importance statistique

- [ ] Corrélation Pearson / Spearman
- [ ] Mutual information si utile
- [ ] Feature importance via modèle arbre

## Interprétation

- [ ] Expliquer pourquoi certaines features sont importantes
- [ ] Identifier les variables peu utiles

---

# 4. Feature Selection

## Suppression

- [ ] retirer variables inutiles
- [ ] retirer variables redondantes
- [ ] retirer leakage potentiel

## Justification

- [ ] expliquer chaque suppression

---

# 5. Feature Engineering 

## Création de nouvelles features

Exemples possibles :

- [ ] total support score
- [ ] academic risk score
- [ ] attendance quality
- [ ] lifestyle score
- [ ] parent education combined score

## Transformation

- [ ] log transform si nécessaire
- [ ] binning si pertinent
- [ ] regroupement de catégories rares

## Vérification

- [ ] vérifier si cela améliore réellement le modèle

---

# 6. Data Preprocessing

## Missing Values

- [ ] décider :
  - [ ] suppression
  - [ ] imputation moyenne
  - [ ] médiane
  - [ ] mode
  - [ ] autre

## Outliers

- [ ] détecter
- [ ] décider :
  - [ ] garder
  - [ ] supprimer
  - [ ] capper

## Encodage catégoriel

Choisir correctement :

- [ ] One-Hot Encoding
- [ ] Label Encoding
- [ ] Ordinal Encoding

Attention :
- [ ] éviter data leakage

## Scaling

- [ ] StandardScaler
ou
- [ ] MinMaxScaler

Selon le modèle utilisé

---

# 7. Baseline Model

IMPORTANT (explicitement demandé)

## Construire baseline simple

Exemples :

- [ ] moyenne globale des notes
ou
- [ ] moyenne par groupe simple

## Calculer performances baseline

- [ ] MAE
- [ ] RMSE
- [ ] R²

## Comparer tous les modèles à cette baseline

---

# 8. Dataset Splitting

## Split correct

- [ ] train / validation / test

Exemple :
- [ ] 70 / 15 / 15

ou

- [ ] train/test + cross-validation

## Vérifier absence de data leakage

Très important

---

# 9. Model Training

Minimum attendu :
- 3 modèles
- dont 1 deep learning

## Modèles classiques à tester

- [ ] Linear Regression
- [ ] Ridge / Lasso
- [ ] Decision Tree Regressor
- [ ] Random Forest Regressor
- [ ] XGBoost / Gradient Boosting
- [ ] SVR
- [ ] KNN Regressor

## Deep Learning

- [ ] MLPRegressor
ou
- [ ] petit réseau de neurones avec Keras / PyTorch

## Justification

- [ ] expliquer pourquoi ces modèles

---

# 10. Hyperparameter Tuning

## Cross-validation

- [ ] K-Fold CV

## Tuning

- [ ] GridSearchCV
ou
- [ ] RandomizedSearchCV

Exemples :

### Random Forest

- [ ] n_estimators
- [ ] max_depth
- [ ] min_samples_split

### XGBoost

- [ ] learning_rate
- [ ] max_depth
- [ ] estimators

### Neural Network

- [ ] nombre de couches
- [ ] neurones
- [ ] learning rate
- [ ] batch size

---

# 11. Performance Comparison

## Métriques principales

- [ ] MAE
- [ ] RMSE
- [ ] R²

## Métriques métier

- [ ] précision détection étudiants <50
- [ ] recall étudiants à risque

Très important pour le vrai besoin métier

## Visualisations

- [ ] tableau comparatif
- [ ] graphique des performances
- [ ] predicted vs actual plot
- [ ] residual plot

---

# 12. Overfitting / Underfitting Analysis

## Vérification

- [ ] train score vs validation score
- [ ] learning curves

## Si overfitting

- [ ] simplifier modèle
- [ ] régularisation
- [ ] plus de données
- [ ] pruning

## Si underfitting

- [ ] modèle plus complexe
- [ ] meilleures features

---

# 13. Conclusions Critiques

- [ ] limites du dataset
- [ ] biais possibles
- [ ] limites des modèles
- [ ] risques métier
- [ ] faux positifs / faux négatifs
- [ ] améliorations futures

---

# 14. Rapport

## table de matière que je pourrais faire

- [ ] Introduction
- [ ] Dataset description
- [ ] EDA
- [ ] Feature selection and engineering
- [ ] Preprocessing
- [ ] Baseline
- [ ] Models tested
- [ ] Hyperparameter tuning
- [ ] Results comparison
- [ ] Overfitting analysis
- [ ] Critical discussion
- [ ] Conclusion

## checklist du rapport

- [ ] max 10 pages
- [ ] graphiques propres
- [ ] analyse critique présente
- [ ] justifications techniques
- [ ] résultats reproductibles
- [ ] code propre et compréhensible

---

# TIPS du prof

- justifier les choix si possible
- comparer les models -> donc faire une baseline
- 