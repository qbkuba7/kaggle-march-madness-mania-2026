# 🏀 Kaggle March Machine Learning Mania - Top 9% Solution

**🏆 Competition:** [Kaggle March Machine Learning Mania 2026](https://www.kaggle.com/competitions/march-machine-learning-mania-2026)

**👨‍💻 Our Kaggle Profiles:** [kubasscala](https://www.kaggle.com/kubasscala), [KTomczyk](https://www.kaggle.com/ktomczyk)

## 👥 Authors
* [Jakub Miszczak](https://github.com/qbkuba7)
* [Kacper Tomczyk](https://github.com/ktomczyk)

## 📌 Short Description
This repository contains our solution for the **Kaggle March Machine Learning Mania 2026** competition. Our primary model achieved a rank of **289 out of 3462** teams, placing us in the **Top 9%** (Bronze Medal zone) of the final leaderboard.

## 🏀 Competition Introduction
The goal of the Kaggle March Madness competition is to forecast the outcomes of all possible matchups in the NCAA Division I Basketball Championships. Instead of simply predicting the winner, participants are required to submit the *probability* of one team beating another. 

The submissions are evaluated using the **Brier Score**, which heavily penalizes confident but incorrect predictions. This requires not only building an accurate predictive model but also properly calibrating the output probabilities.

## 🧠 Our Solution & Methodology

### Data Preprocessing & Feature Engineering
* *Opisz krótko: Jakie dane z Kaggle wykorzystaliście (np. regular season stats, kenpom data)?*
* *Opisz krótko: Jakie nowe zmienne stworzyliście (np. rolling averages, offensive/defensive ratings)?*

### Modeling Strategy
* *Opisz krótko: Jakich modeli użyliście (XGBoost, LightGBM, regresja logistyczna)?*
* *Opisz krótko: Dlaczego akurat te modele? Jak wyglądało strojenie hiperparametrów?*

### Validation
* *Opisz krótko: Jak walidowaliście model, żeby uniknąć overfittingu (np. walidacja na historycznych turniejach z poprzednich lat)?*

## 🏆 Final Results
Although we were quite confident with adding betting odds to our model, we couldn't be entirely sure if it would actually improve our final score. To minimize the risk, we decided to send two final submissions: one incorporating the odds, and a 'clean' baseline model without them.
Here is how they performed in the final standings:

| Submission | Rank | Percentile | Leaderboard |
| :--- | :--- | :--- | :--- |
| **Model 1 (with betting odds)** | **289 / 3462** | **Top 9%** 🥉 | Private |
| **Model 2 (base model)** | 450 / 3462 | Top 13% | Private |

## 🚀 How to Run
1. Clone this repository: 
   ```bash
   git clone [https://github.com/TWOJ_LOGIN/TWOJE_REPOZYTORIUM.git](https://github.com/TWOJ_LOGIN/TWOJE_REPOZYTORIUM.git)
