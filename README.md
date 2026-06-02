# EV Lithium-Ion Battery State of Health Estimation using Machine Learning

## Overview

This repository presents a research-style documentation project on **State of Health (SOH) estimation for EV lithium-ion batteries** using machine learning techniques.

The project is based on my B.Tech final year project, **“Li-Ion Battery SOH Prediction using ML,”** and my published research work, **“EV Lithium-Ion Battery SOH Estimation based on LightGBM Model.”**

The work focuses on battery diagnostic data analysis, SOH calculation methodology, feature engineering, machine learning-based prediction, model evaluation, and visualization.

> Note: This public repository is intended to document the methodology, research workflow, and results. The full implementation code and experimental notebooks are not publicly disclosed.

---

# EV Lithium-Ion Battery State of Health Estimation using Machine Learning

![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Battery%20SOH-blue)
![Model](https://img.shields.io/badge/Models-XGBoost%20%7C%20LightGBM-green)
![Domain](https://img.shields.io/badge/Domain-EV%20Battery%20Diagnostics-orange)
![Status](https://img.shields.io/badge/Status-Research%20Documentation-lightgrey)
![Code](https://img.shields.io/badge/Code-Private-red)

---

## Documentation

- [Methodology](docs/methodology.md)
- [Results Summary](docs/results-summary.md)
- [Publication and Patent](docs/publication-and-patent.md)

---

## Problem Statement

Lithium-ion batteries degrade over time due to charge-discharge cycles, operating conditions, temperature variation, charging behavior, and usage patterns.

Accurate estimation of battery State of Health is important for:

* Battery Management Systems
* Predictive maintenance
* Electric vehicle reliability
* Energy storage safety
* Battery lifecycle optimization
* Remaining Useful Life assessment

This project explores how machine learning can estimate SOH using Battery Management System data and charging behavior.

---

## Project Background

The original B.Tech final year project focused on developing an SOH calculation methodology and applying **XGBoost** for SOH prediction.

The research paper extended the work using **LightGBM**, a gradient boosting algorithm suitable for large-scale structured battery datasets.

The overall workflow includes:

1. Battery data acquisition
2. Data preprocessing
3. Energy and unit calculation
4. Charge cycle identification
5. Window-based SOC analysis
6. SOH calculation
7. Feature selection
8. XGBoost-based prediction
9. LightGBM-based estimation
10. Model evaluation and visualization

---

## Dataset Description

The research work used charging data from **20 commercial electric vehicles**, containing more than **16 million battery observations**.

Dataset: [Dataset Link](https://github.com/TengMichael/battery-charging-data-of-on-road-electric-vehicles/?tab=readme-ov-file)
The dataset included parameters such as:

* Record time
* State of Charge
* Pack voltage
* Charging current
* Maximum cell voltage
* Minimum cell voltage
* Maximum temperature
* Minimum temperature
* Available energy
* Available capacity
* Charge cycle information

Due to dataset size and implementation privacy, the raw dataset and full source code are not included in this public repository. But the link is been provided in Data set description.

---

## SOH Calculation Methodology

The final year project introduced a window-based SOH calculation approach.

The methodology involved:

* Segmenting the State of Charge range into windows
* Computing energy consumption during charging
* Calculating cumulative units within SOC windows
* Creating a best-performance benchmark dataset
* Comparing current battery behavior against benchmark performance
* Estimating SOH as a normalized battery health indicator

A simplified representation of the SOH calculation is:

```text
SOH = (Cumulative Window Units in Current Dataset / Cumulative Window Units in Best Performance Dataset) × 100
```

This approach allows SOH to be evaluated relative to optimal battery behavior across SOC windows.

### This SOH Calculation Methodology has a granted patented. In (SA Patents, 2024): “A System and Method for Calculation of State of Health of Li-Ion Battery”.  
---

## Machine Learning Approach

### XGBoost Model

The initial project used **XGBoost** for SOH prediction because it performs well on structured datasets and can capture non-linear relationships between battery parameters.

The XGBoost workflow included:

* Feature selection
* Data preprocessing
* Train-test split
* GridSearchCV-based hyperparameter tuning
* Regression model training
* Evaluation using MSE, MAE, and R² score

### LightGBM Model

The research paper used **LightGBM** for efficient SOH estimation on large-scale EV battery data.

The LightGBM workflow included:

* Data preparation
* 80:20 train-test split
* Model initialization
* Hyperparameter tuning using Grid Search CV
* Final model training
* Regression-based evaluation
* Visualization of actual vs predicted SOH

Selected LightGBM hyperparameters:

| Hyperparameter       | Selected Value |
| -------------------- | -------------: |
| Number of Estimators |            200 |
| Learning Rate        |            0.2 |
| Maximum Tree Depth   |              3 |

---

## Model Evaluation

The LightGBM model achieved the following results:

| Metric              | Result |
| ------------------- | -----: |
| Mean Squared Error  |  1.894 |
| Mean Absolute Error |  1.016 |
| R² Score            | 0.9069 |

The model explained approximately **90.69% of the variance** in SOH values, demonstrating strong predictive performance for battery health estimation.

---

## Visual Analysis

The project included the following visual analyses:

* Correlation matrix analysis
* Actual SOH vs predicted SOH comparison
* Charge cycle vs SOH trend analysis
* Polynomial regression curve visualization
* Model performance interpretation

These visualizations helped evaluate how closely the predicted SOH followed actual battery degradation trends over charge cycles.

---

## Applications

This project has potential applications in:

* Electric vehicle battery health monitoring
* Predictive maintenance systems
* Battery Management Systems
* Industrial energy storage systems
* Charging infrastructure optimization
* Battery lifecycle analysis
* Research and development in battery diagnostics

---

## Research Output

This project is connected to the following academic and innovation outcomes:

* B.Tech Final Year Project: **Li-Ion Battery SOH Prediction using ML**
* Published Research Paper: **EV Lithium-Ion Battery SOH Estimation based on LightGBM Model**
* Patent: **A System and Method for Calculation of State of Health of Li-Ion Battery**

---

## Code Availability

The full implementation code, experimental notebooks, and detailed development files are maintained separately and are not publicly available in this repository.

This public repository is intended to present the methodology, technical workflow, model results, and research contribution without exposing private implementation details.

Access to implementation details may be provided selectively for academic, professional, or review purposes.

---

## Author

**Mayur More**
MSc Data Science, AI & Digital Business
Berlin, Germany

GitHub: [mayurmore0812](https://github.com/mayurmore0812)
LinkedIn: [linkedin.com/in/mayurmore0812](https://www.linkedin.com/in/mayurmore0812)
