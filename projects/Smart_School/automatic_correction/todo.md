# TODO — Projet AI/ML Smart School (Partie 2 : Automatic Correction / OCR)

## Contexte

Le projet sera réalisé principalement avec :

- Kaggle Notebook
- Python
- pandas / numpy
- matplotlib / seaborn
- scikit-learn
- TensorFlow / Keras

Objectif :

Construire un système d’OCR capable de reconnaître automatiquement les caractères manuscrits des étudiants afin d’automatiser la correction des examens.

Le problème principal est :

- classification d’images (reconnaissance de caractères manuscrits)

Le modèle devra être capable de reconnaître correctement les chiffres et/ou lettres du dataset fourni.

---

# PLAN GLOBAL

- [ ] Importer et comprendre le dataset OCR
- [ ] Préparer correctement les données
- [ ] Visualiser les images et vérifier leur qualité
- [ ] Prétraiter les images
- [ ] Construire plusieurs modèles de classification
- [ ] Construire un modèle Deep Learning avec TensorFlow / Keras (CNN recommandé)
- [ ] Comparer les performances
- [ ] Utiliser une confusion matrix pour l’évaluation
- [ ] Analyser les erreurs du modèle
- [ ] Produire les graphiques pour le rapport
- [ ] Rédiger la partie OCR du rapport

---

# 1. Setup Kaggle Notebook

- [ ] Créer le notebook Kaggle OCR
- [ ] Importer les librairies nécessaires
- [ ] Vérifier TensorFlow et accès GPU

---

# 2. Compréhension du Dataset

- [ ] Charger le dataset
- [ ] Identifier :
  - [ ] nombre d’images
  - [ ] taille des images
  - [ ] nombre de classes
  - [ ] labels disponibles
  - [ ] répartition des classes

- [ ] Vérifier :
  - [ ] valeurs manquantes
  - [ ] images corrompues
  - [ ] déséquilibre entre classes

---

# 3. Visualisation des Données

- [ ] Afficher plusieurs exemples d’images
- [ ] Vérifier si les caractères sont bien lisibles
- [ ] Observer les cas difficiles :
  - [ ] écriture peu lisible
  - [ ] bruit
  - [ ] variations importantes entre samples

- [ ] Vérifier si certaines classes sont souvent ambiguës

---

# 4. Préprocessing

- [ ] Normaliser les pixels
- [ ] Reshape des images pour Keras
- [ ] Encoder les labels
- [ ] Split train / validation / test

Si nécessaire :

- [ ] resize
- [ ] binarisation
- [ ] noise reduction
- [ ] data augmentation

---

# 5. Baseline Model

- [ ] Construire une baseline simple

Exemples :

- [ ] Logistic Regression
- [ ] Random Forest
- [ ] MLP simple

Objectif :

Comparer le CNN avec un modèle plus simple

---

# 6. Modèle Deep Learning (Principal)

## CNN avec TensorFlow / Keras

- [ ] Construire un CNN adapté

Exemple :

- [ ] Conv2D
- [ ] MaxPooling
- [ ] Dropout
- [ ] Dense
- [ ] Softmax final

- [ ] Choisir :
  - [ ] optimizer
  - [ ] loss function
  - [ ] batch size
  - [ ] epochs

- [ ] Utiliser EarlyStopping si utile

---

# 7. Hyperparameter Tuning

- [ ] Tester plusieurs architectures

Exemples :

- [ ] nombre de couches
- [ ] taille des filtres
- [ ] nombre de neurones
- [ ] dropout
- [ ] learning rate
- [ ] batch size

Objectif :

Trouver le meilleur compromis performance / overfitting

---

# 8. Évaluation des Performances

## Métriques principales

- [ ] Accuracy
- [ ] Precision
- [ ] Recall
- [ ] F1-score

## Outil important

- [ ] Confusion Matrix

Très important car explicitement conseillé dans l’énoncé

## Visualisations

- [ ] train loss / validation loss
- [ ] train accuracy / validation accuracy
- [ ] confusion matrix
- [ ] exemples de prédictions correctes / incorrectes

---

# 9. Analyse des Erreurs

- [ ] Identifier les classes les plus confondues
- [ ] Expliquer pourquoi certaines erreurs arrivent

Exemples :

- [ ] chiffres visuellement proches
- [ ] mauvaise qualité d’écriture
- [ ] bruit dans l’image

- [ ] Proposer des pistes d’amélioration

---

# 10. Overfitting / Underfitting

- [ ] Comparer train vs validation

Si overfitting :

- [ ] dropout
- [ ] augmentation
- [ ] simplifier le modèle

Si underfitting :

- [ ] modèle plus complexe
- [ ] meilleures features
- [ ] plus d’epochs

---

# 11. Discussion Critique

- [ ] limites du dataset
- [ ] limites du modèle
- [ ] difficultés réelles d’un OCR scolaire
- [ ] cas où le système peut échouer
- [ ] impact sur la correction automatique
- [ ] améliorations futures

---

# 12. Rapport

## table des matières

- [ ] Introduction OCR
- [ ] Dataset description
- [ ] Dataset preparation
- [ ] Preprocessing
- [ ] Baseline
- [ ] CNN model
- [ ] Hyperparameter tuning
- [ ] Results
- [ ] Confusion matrix analysis
- [ ] Error analysis
- [ ] Critical discussion
- [ ] Conclusion

---

# TIPS

- utiliser une confusion matrix 