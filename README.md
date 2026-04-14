# 🏀 Kaggle March Machine Learning Mania - Top 9% Solution

**🏆 Competition:** [Kaggle March Machine Learning Mania 2026](https://www.kaggle.com/competitions/march-machine-learning-mania-2026)

**👨‍💻 Our Kaggle Profiles:** [kubasscala](https://www.kaggle.com/kubasscala), [KTomczyk](https://www.kaggle.com/ktomczyk)

> [!IMPORTANT]
> **Disclaimer:** The competition ended just a few days ago. We are currently in the process of cleaning up the code, organizing the final files, and updating the documentation. This repository may undergo further changes to ensure everything is clear and reproducible.

## 👥 Authors
* [Jakub Miszczak](https://github.com/qbkuba7)
* [Kacper Tomczyk](https://github.com/kacpert20)

## 📌 Short Description
This repository contains our solution for the **Kaggle March Machine Learning Mania 2026** competition. Our primary model achieved a rank of **289 out of 3462** teams, placing us in the **Top 9%** (Bronze Medal zone) of the final leaderboard.

## 📂 Project Structure
The solution is organized in two main Jupyter notebooks:

* **`notebook_1_kaggle.ipynb`**: TODO...
* **`notebook_2_kaggle.ipynb`**: The core of the solution. It contains chosen models training (ElasticNet & HistGradientBoosting), hyperparameter tuning, and the logic for blending model predictions with external betting market data.

## 🏀 Competition Introduction
The goal of the Kaggle March Madness competition is to forecast the outcomes of all possible matchups in the NCAA Division I Basketball Championships. Instead of simply predicting the winner, participants are required to submit the *probability* of one team beating another. 

The submissions are evaluated using the **Brier Score**, which heavily penalizes confident but incorrect predictions. This requires not only building an accurate predictive model but also properly calibrating the output probabilities.

## 🧠 Our Solution & Methodology


### Data Preprocessing & Feature Engineering
We separated training processes for the Men's and Women's tournaments to account for different dataset characteristics. This was the only logical approach, as men's and women's basketball are completely different so different stats carry different weights, and separate models allow for capturing these unique dynamics, which led us to better results.
#### TODO...


### 🧠 Optimized Modeling Strategy

Since men’s and women’s basketball have different dynamics, it was clear for us that we have to check many different models both for men's and women's predictions. We checked many models such as: XGBoost, SVM, Standard Logistic Regression, ElasticNet, MLP etc.) and trained them to see how these models predict on historical data and this allowed us to choose the best model and preprocessing for each tournament.

* **Men’s Tournament (ElasticNet Regression):** For the men's games, we used **Logistic Regression** with **ElasticNet** regularization. This method balances two types of penalties (L1 and L2), which helps the model focus on the most important stats and ignore "noise." It’s a great way to prevent the model from overcomplicating things (overfitting).
* **Women’s Tournament (HistGradientBoosting):** For the women's games, we chose the **HistGradientBoostingClassifier**. This is a powerful decision-tree-based model that is very good at finding complex, non-linear patterns in the data. It is also faster and more stable when working with larger datasets.
* **Fine-Tuning:** We didn't just use default settings. We performed **hyperparameter optimization** to find the exact values for parameters like `C`, `l1_ratio`, and `learning_rate`. This ensured that both models were precisely tuned, leading to much more reliable probability estimates.

### ⚙️ Calibration

After training the models, we performed one last step before submitting our predictions to ensure they would give as good result as possible.

* **Brier Score & Probability Clipping:** The competition is scored using the **Brier Score**, which measures how accurate the predicted probabilities are. To get a better score, we used a technique called **clipping**. This means the model never predicts a 0% or 100% chance. We knew that in sports, surprises always happen, and being 100% wrong would result in a very high penalty in our Brier Score.



### 💡 External Data

In this competition, besides the data provided by Kaggle, it was also allowed to use external data found on the internet, as long as it was publicly available for everyone and for free. 

We decided to compare our solution with **betting odds** and use them to improve our model. The average deviation of our model's predictions from the bookmakers' odds was **7.5% for the men's tournament** and **11.3% for the women's**, so we were very satisfied that our model predicts probabilities so accurately. 

For the first phase of the tournament, the matches were drawn in advance. For these games, we had exact betting odds from which we calculated the win probabilities according to the bookmakers. This made our model for the first phase much more accurate. For the remaining matches, we used the tournament-winning odds also publicly available online (e.g., from **ESPN**). Based on this, we combined the predictions of our base model with the bookmaker's predictions to get our final model.

## 🏆 Final Results
Although we were quite confident with adding betting odds to our model, we couldn't be entirely sure if it would actually improve our final score. To minimize the risk, we decided to send two final submissions: one incorporating the odds, and a 'clean' baseline model without them.
Here is how they both performed in the final standings:

| Submission | Rank | Percentile |
| :--- | :--- | :--- |
| **Model 1 (with betting odds)** | **289 / 3462** | **Top 9%** 🥉 |
| **Model 2 (base model)** | 450 / 3462 | Top 13% |
