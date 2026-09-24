# 🏥 HealthConnect Clinic - Week 8 Data Science

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![AnalystLab Africa](https://img.shields.io/badge/AnalystLab-Africa-orange.svg)](https://analystlab.africa)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

---

## 📋 Table des Matières

1. [Présentation du Projet](#-présentation-du-projet)
2. [Structure du Dépôt](#-structure-du-dépôt)
3. [Résultats Finaux](#-résultats-finaux)
4. [Modèle Final](#-modèle-final)
5. [Interprétation Business](#-interprétation-business)
6. [Collaboration HC-POD](#-collaboration-hc-pod)
7. [Limites et Risques](#-limites-et-risques)
8. [Présentation Vidéo](#-présentation-vidéo)
9. [Technologies](#-technologies)
10. [Contact](#-contact)

---

## 🎯 Présentation du Projet

**HealthConnect Clinic** fait face à un défi majeur : **45% de rendez-vous manqués** (No-Show).

L'objectif est de développer un modèle de Machine Learning pour prédire les No-Show.

### Problème ML

| Élément | Description |
|---------|-------------|
| **Type** | Classification binaire |
| **Cible** | `no_show` (1 = manqué, 0 = présent) |
| **Métrique principale** | F1-Score |
| **Objectif Week 8** | Finaliser, intégrer et présenter |

---

## 📁 Structure du Dépôt


---

## 📊 Résultats Finaux

### Performance du Modèle Final

| Métrique | Seuil 0.50 | Seuil 0.30 | Amélioration |
|----------|------------|------------|--------------|
| Accuracy | 62.13% | 62.13% | - |
| Precision | 62.07% | 62.07% | - |
| Recall | 66.80% | 66.80% | - |
| **F1-Score** | **64.35%** | **69.45%** | **+5.10%** |
| ROC-AUC | 66.02% | 66.02% | - |

### Tests de Validation

| Test | Résultat | Critère | Statut |
|------|----------|---------|--------|
| Cross-validation 10-fold | 0.6448 | > 0.65 | ❌ (proche) |
| Généralisation | 0.6336 | > 0.65 | ❌ (proche) |
| Stabilité | 0.0186 | < 0.02 | ✅ |
| Optimisation seuil | 0.6945 | > 0.70 | ❌ (proche) |
| Performance segment | 0.61-0.66 | > 0.60 | ✅ |
| Overfitting | 0.0014 | < 0.05 | ✅ |

**📌 Bilan : 3 PASS / 3 FAIL** — Tous les FAIL sont très proches des objectifs.

---

## 🏆 Modèle Final

### Modèle Sélectionné

**Baseline (Logistic Regression)**

| Paramètre | Valeur |
|-----------|--------|
| Algorithme | Logistic Regression |
| `max_iter` | 1000 |
| `random_state` | 42 |
| `class_weight` | balanced |
| `penalty` | l2 |
| Seuil de déploiement | 0.30 |

### Justification

- ✅ Meilleur F1-Score (64.35%)
- ✅ Meilleur Recall (66.80%)
- ✅ Meilleur au seuil optimal (69.45%)
- ✅ Plus stable (écart-type < 0.02)
- ✅ Pas d'overfitting
- ✅ Interprétable

### Features les Plus Importantes

| Rang | Feature | Coefficient | Impact |
|------|---------|-------------|--------|
| 1 | `previous_no_shows` | +0.85 | Très fort |
| 2 | `has_previous_no_show` | +0.72 | Très fort |
| 3 | `booking_lead_days` | +0.45 | Modéré |
| 4 | `distance_to_clinic_km` | +0.32 | Modéré |
| 5 | `reminder_sent_encoded` | -0.18 | Faible |

---

## 💼 Interprétation Business

### Valeur Business

| Aspect | Impact |
|--------|--------|
| Réduction des No-Show | Détecte 66.80% des absences |
| Interventions ciblées | Rappels personnalisés |
| Optimisation des créneaux | Meilleure utilisation |
| Expérience patient | Meilleur suivi |

### Recommandations

1. 🔴 Utiliser le seuil de 0.30
2. 🔴 Cibler les patients avec historique d'absence
3. 🟡 Réduire les délais de réservation
4. 🟡 Proposer des téléconsultations
5. 🟡 Renforcer les rappels

---

## 🤝 Collaboration HC-POD

### Partenaire : Data Analytics

| # | Élément | Détail |
|---|---------|--------|
| 1 | Track collaboré | Data Analytics |
| 2 | Dépendance | KPIs → Interprétation |
| 3 | Reçu | KPIs validés, insights |
| 4 | Fourni | Feature importance, seuils |
| 5 | Test | Validation croisée |
| 6 | Changement | +5.1 points de F1 |
| 7 | Preuve | Document + capture |

---

## ⚠️ Limites et Risques

### Limites

| Limite | Description |
|--------|-------------|
| Performance | F1 = 0.6945 (objectif: 0.70) |
| Faux Négatifs | 161 cas non détectés |
| Données | Fictives |
| Modélisation | Linéaire |

### Risques

| Risque | Mitigation |
|--------|------------|
| Faux Positifs | Ajuster le seuil |
| Faux Négatifs | Features supplémentaires |
| Dérive | Suivi et ré-entraînement |

---

## 🎬 Présentation Vidéo

### Structure (5-10 minutes)

| Section | Durée | Contenu |
|---------|-------|---------|
| 1. Introduction | 30-60 sec | Nom, track, projet |
| 2. Contribution | 2-3 min | Modèle, méthodes, résultats |
| 3. Collaboration | 1-2 min | HC-POD, échanges |
| 4. Tests | 1-2 min | Tests, raffinement |
| 5. Solution Globale | 1-2 min | Intégration, valeur |
| 6. Conclusion | 30-60 sec | Takeaway |

---

## 🛠️ Technologies

| Technologie | Version |
|-------------|---------|
| Python | 3.8+ |
| Pandas | 1.5.0 |
| NumPy | 1.23.0 |
| Scikit-learn | 1.2.0 |
| Matplotlib | 3.6.0 |
| Seaborn | 0.12.0 |
| Jupyter | - |

---

## 📞 Contact

- **Nom** : SOGA Para
- **Email** : sparadodaniel@gmail.com
- **Programme** : AnalystLab Africa
- **Track** : Data Science

---

## 📌 Tags

`#DataScience` `#MachineLearning` `#Healthcare` `#AnalystLabAfrica` 
`#HealthConnect` `#Python` `#Classification` `#LogisticRegression` 
`#FinalProject` `#NoShowPrediction`

---

**Fait avec ❤️ dans le cadre du programme AnalystLab Africa Experience Lab**
