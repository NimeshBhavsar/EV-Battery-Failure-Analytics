# EV Battery Failure Analytics

This notebook is a complete exploratory data analysis and machine learning workflow for predicting electric vehicle (EV) battery failures using telemetry, battery health indicators, charging behavior, environmental exposure, and diagnostic warnings.

## Project Objective

The goal is to build a binary classification model that predicts whether an EV battery will fail:

- 0 = Healthy / no failure
- 1 = Battery failure

This is useful for:

- predictive maintenance
- battery lifecycle monitoring
- warranty risk reduction
- fleet management optimization
- early warning detection for thermal or electrical degradation

## Dataset

The notebook expects a CSV dataset named:

- `ev_battery_failure_dataset.csv`
- 
https://www.kaggle.com/datasets/sarveshchhetri/ev-battery-failure-prediction-dataset-200k?select=ev_battery_failure_dataset.csv

The dataset contains approximately 200,000 EV records and 70+ features spanning:

- vehicle metadata
- battery specifications
- usage history
- charging patterns
- thermal and electrical diagnostics
- environmental operating conditions
- fault and BMS warning data

Key target variable:

- `battery_failure`

## Notebook Workflow

The notebook is organized into a full analytical pipeline:

### 1. Problem framing and dataset overview

Introduces the business problem and explains why EV battery failure prediction is important.

### 2. Data cleaning and preprocessing

- loads the dataset
- inspects structure and missing values
- removes non-predictive identifiers
- imputes missing numeric and categorical values
- prepares the dataset for modeling

### 3. Exploratory data analysis

A large set of visualizations is generated, including:

- histograms
- line plots
- bar plots
- pie charts
- box plots
- violin plots
- scatter plots
- pair plots

These visualizations focus on patterns such as:

- battery degradation over time
- thermal stress and overheating
- voltage imbalance
- charging intensity and capacity loss
- fleet vs private usage patterns
- failure distribution by battery chemistry and manufacturer

### 4. Feature engineering

New engineered features are created to capture domain-specific risk signals, including:

- thermal stress index
- fast-charge stress
- voltage risk score
- degradation per cycle
- total alarm count

### 5. Machine learning models

The notebook trains and compares several classifiers:

- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting

It evaluates them using:

- accuracy
- precision
- recall
- F1-score
- ROC-AUC
- confusion matrix

### 6. Interpretability and diagnostics

The notebook also includes explanatory plots to highlight the most important variables influencing battery failure, such as:

- feature importance ranking
- cumulative importance curves
- SHAP-style proxy explanations
- LIME-style local explanations
- model stability checks

### 7. Ensemble diagnostics

It compares additional ensemble approaches:

- Random Forest
- Gradient Boosting
- AdaBoost
- Stacking Classifier

with plots for:

- ROC curves
- precision-recall curves
- calibration curves
- learning convergence
- stacking separation analysis

### 8. Anomaly detection and clustering

The notebook explores unsupervised techniques for identifying abnormal battery behavior:

- Isolation Forest
- Local Outlier Factor
- Elliptic Envelope
- K-Means
- DBSCAN
- Agglomerative Clustering

These are used to identify abnormal operational profiles, risk clusters, and high-risk battery states.

### 9. Final conclusions

The notebook ends with a summary of:

- key drivers of failure
- practical use cases in EV operations and manufacturing
- next steps for real-world deployment
- recommendations for deeper time-series or edge-AI deployment

## Key Risk Signals Identified

Across the analysis, the strongest indicators of battery failure are typically linked to:

- rising internal resistance
- elevated battery temperature
- high thermal runaway risk
- voltage imbalance across cells
- high fast-charge usage ratios
- frequent BMS warnings and alarms
- severe degradation and capacity loss

## Requirements

This notebook uses common Python data science libraries, including:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

You should have a Python environment with these packages installed.

## Suggested Execution Order

Run all cells in order from top to bottom. The notebook is designed as a sequential analytical pipeline, and later sections depend on earlier output and transformations.

## Notes

- Some sections use sampled subsets of the dataset for plotting speed and computational efficiency.
- The notebook contains the full data science workflow but is primarily exploratory and demonstrative.
- The dataset path is hardcoded in several cells, so ensure the CSV is available in the expected location when running the notebook.

## Typical Use Cases

This notebook can be used for:

- academic battery analytics projects
- EV reliability and safety analysis
- predictive maintenance experimentation
- business case development for fleet optimization
- research demonstrating failure-risk modeling in lithium-ion battery systems

## Summary

This project is a practical end-to-end EV battery risk analytics notebook that combines statistical exploration, feature engineering, machine learning, interpretability, and anomaly detection to identify battery failure patterns and support decision-making in EV operations and safety management.
