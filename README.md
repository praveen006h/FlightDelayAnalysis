# Flight Delay Analysis ✈️

This repository contains an end-to-end machine learning project to predict whether a flight arrival will be delayed. It explores data preprocessing, feature engineering, and the evaluation of various classification models.

## 🎯 Objective
* **Goal**: Predict whether a flight arrival will be delayed by 3 minutes or more.
* **Target Variable**: Binarized `ARRIVAL_DELAY`.
  * `0`: Arrival delay < 3 minutes
  * `1`: Arrival delay $\ge$ 3 minutes
* **Scope**: Analysis focuses on flights from January to manage computational resources while preserving seasonal patterns.

## 📊 Dataset
The dataset used is the **Kaggle USDOT Flight Delays Dataset (2015)**.
* **Dataset Link**: [Kaggle Flight Delays](https://www.kaggle.com/datasets/usdot/flight-delays)
* **Colab Notebook Reference**: [Link](https://colab.research.google.com/drive/1mNRqiqkB7S-rqLFZ7p1zm5ytQ0_XQz_i#scrollTo=RTvJWdixA0B4)

The dataset includes:
* `flights.csv`: Core flight details (departure/arrival times, delays, distance, etc.).
* `airlines.csv`: Carrier IATA codes mapped to full names.
* `airports.csv`: Airport codes mapped to names, cities, states, and coordinates.

## 🛠️ Preprocessing & Feature Engineering
* **Data Selection**: Dropped missing values and filtered out extreme delay outliers ($\ge$ 500 minutes).
* **Train/Val/Test Split**: 70% Train, 10% Validation, 20% Test (stratified).
* **Cyclic Time/Date Encoding**: Employed trigonometric conversion (sine/cosine) for time/date variables (hour, minute, day) to capture periodicity.
* **Categorical Encoding**: Label Encoding + One-Hot Encoding for airlines.

## 🧠 Models Evaluated
Six classification models were evaluated and tuned using `GridSearchCV` with 3-fold cross-validation:
1. Decision Tree Classifier
2. Logistic Regression
3. SGD Classifier
4. Gaussian Naive Bayes
5. Random Forest Classifier
6. XGBoost Classifier

## 📈 Evaluation
Models were assessed using:
* Test Accuracy
* Confusion Matrices
* ROC-AUC Curves
* Visualizations including delay heatmaps, distance vs. delay curves, and XGBoost feature importances.
