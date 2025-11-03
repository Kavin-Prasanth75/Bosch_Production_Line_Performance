Bosch Production Line Performance 

This repository presents a comprehensive machine learning workflow for predicting manufacturing failures using Bosch’s production line data.
The project benchmarks XGBoost, Random Forest, and LightGBM models to identify the best-performing classifier.

🧠 Overview

Bosch records hundreds of measurements at every step of its manufacturing process. Using this massive dataset, the goal is to predict product failure (Response = 1) before final testing.

Due to the dataset’s high dimensionality and size (millions of samples), the workflow focuses on:

Memory-efficient data loading

Feature engineering from timestamp and numeric data

Ensemble model training (XGBoost, Random Forest, LightGBM)

⚙️ Project Workflow
1. Data Loading

Reads CSVs (train_numeric.csv, train_categorical.csv, train_date.csv) using chunking for memory efficiency.

Selects relevant columns based on variance and completeness.

2. Feature Engineering

Computes start and end stations from timestamps.

Selects numeric features with significant variance.

Encodes categorical features if applicable.

Creates additional features such as processing time or station range.

3. Model Training

Three models are trained and compared:

Model	Description	Key Hyperparameters
XGBoost	Gradient boosting on trees	max_depth, learning_rate, subsample
Random Forest	Bagging-based ensemble	n_estimators, max_features
LightGBM	Gradient boosting using histogram-based algorithm	num_leaves, max_depth, learning_rate
4. Evaluation

Each model is evaluated on validation data using metrics:

ROC-AUC

F1-Score

Precision / Recall

Confusion Matrix
