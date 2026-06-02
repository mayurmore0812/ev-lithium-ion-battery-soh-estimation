## 1. Methodology Overview

This project focuses on estimating the State of Health (SOH) of EV lithium-ion batteries using battery charging data and machine learning techniques.

The methodology combines battery-domain understanding with data-driven modeling. It includes battery data preprocessing, energy calculation, charge cycle identification, window-based SOH calculation, feature selection, and machine learning-based SOH prediction.

The project was developed in two major stages:


1. **Final Year Project Stage:** XGBoost-based SOH prediction using a custom SOH calculation methodology.

I - SOH Calculation Block Diagram

<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/7e94b4c4-cb2a-4c3d-8d63-639fe9bc425a" />


II - ML XGBOOST Modeling Block Diagram 

<img width="500" height="400" alt="image" src="https://github.com/user-attachments/assets/6d552a7b-563d-4288-9f31-104b6f00b64f" />



2. **Research Paper Stage:** LightGBM-based SOH estimation using large-scale EV battery charging data.

III - ML LIGHTGBM Modeling Block Diagram 

<img width="800" height="300" alt="image" src="https://github.com/user-attachments/assets/69d35bbd-5e0a-496b-a3d4-9516b43f79d0" />


---

## 2. Data Acquisition

The project used Battery Management System data collected from multiple EV lithium-ion batteries.

The dataset included battery parameters such as:

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

These parameters were used to understand battery charging behavior and estimate battery degradation patterns.

---

## 3. Data Preprocessing

Data preprocessing was performed to prepare the raw battery dataset for SOH calculation and machine learning modeling.

The preprocessing stage included:

* Cleaning raw charging data
* Handling missing or inconsistent values
* Selecting relevant battery parameters
* Identifying charging events
* Structuring data by charge cycle
* Preparing features for model training

This step was important because raw Battery Management System data can contain noise, irregular sampling, missing values, and inconsistent charging behavior.

---

## 4. Energy Calculation

Energy consumption during charging was calculated using pack voltage and charging current.

A simplified representation is:

```text
Energy = Pack Voltage × Charging Current
```

This helped capture the energy behavior of the battery during charging.

Energy-based features were important because battery degradation is closely related to how energy is stored, consumed, and transferred during charge cycles.

---

## 5. Charge Cycle Identification

Charge cycles were identified from the charging data to analyze how battery health changes over repeated usage.

A charge cycle represents a charging event from the beginning of charging to the end of charging.

Charge cycle information was important because battery SOH generally decreases as the number of charge cycles increases.

---

## 6. Window-Based SOH Calculation

A key part of the final year project was the custom SOH calculation methodology.

The State of Charge range was divided into multiple windows. Each window represented a specific SOC interval. Energy-related values were calculated within these windows to understand battery performance at different charging stages.

The methodology included:

1. Segmenting SOC into windows
2. Calculating energy and units within each window
3. Computing cumulative window units
4. Creating a best-performance benchmark dataset
5. Comparing current battery behavior with benchmark behavior
6. Calculating SOH as a normalized health indicator

A simplified representation of the SOH calculation is:

```text
SOH = (Cumulative Window Units in Current Dataset / Cumulative Window Units in Best Performance Dataset) × 100
```

This allowed SOH to be calculated relative to the best observed battery performance.

---

## 7. Feature Selection

After SOH calculation, relevant features were selected for machine learning model development.

Important features included:

* State of Charge
* Pack voltage
* Charging current
* Energy
* Available capacity
* Charge cycle
* Window-based calculated parameters
* Actual SOH

Feature selection helped reduce unnecessary input variables and allowed the model to focus on the most meaningful battery health indicators.

---

## 8. XGBoost-Based SOH Prediction

The initial project used XGBoost for SOH prediction.

XGBoost was selected because it performs well on structured tabular datasets and can model non-linear relationships between battery parameters and SOH.

The XGBoost workflow included:

1. Feature selection
2. Data preprocessing
3. Train-test split
4. Hyperparameter tuning using GridSearchCV
5. Model training
6. SOH prediction
7. Model evaluation using regression metrics

The model was evaluated using:

* Mean Squared Error
* Mean Absolute Error
* R² Score

---

## 9. LightGBM-Based SOH Estimation

The research paper extended the project using LightGBM.

LightGBM was selected because it is efficient for large structured datasets and is suitable for gradient boosting-based regression problems.

The LightGBM workflow included:

1. Data preparation
2. 80:20 train-test split
3. Model initialization
4. Hyperparameter tuning using Grid Search Cross Validation
5. Selection of best hyperparameters
6. Final model training
7. Model evaluation
8. Visualization of actual and predicted SOH

The selected LightGBM hyperparameters were:

| Hyperparameter       | Selected Value |
| -------------------- | -------------: |
| Number of Estimators |            200 |
| Learning Rate        |            0.2 |
| Maximum Tree Depth   |              3 |

---

## 10. Model Evaluation

The models were evaluated using regression metrics to measure prediction accuracy.

The main evaluation metrics were:

| Metric              | Purpose                                                     |
| ------------------- | ----------------------------------------------------------- |
| Mean Squared Error  | Measures average squared prediction error                   |
| Mean Absolute Error | Measures average absolute prediction error                  |
| R² Score            | Measures how much variance in SOH is explained by the model |

For the LightGBM research implementation, the reported results were:

| Metric              | Result |
| ------------------- | -----: |
| Mean Squared Error  |  1.894 |
| Mean Absolute Error |  1.016 |
| R² Score            | 0.9069 |

The R² score indicates that the model explained approximately 90.69% of the variance in SOH values.

---

## 11. Visualization and Analysis

The project used visual analysis to understand model performance and battery degradation trends.

The analysis included:

* Correlation matrix analysis
* Actual SOH vs predicted SOH scatter plot
* Charge cycle vs SOH trend visualization
* Polynomial regression curve analysis
* Comparison of actual and predicted degradation patterns

These visualizations helped interpret whether the model was capturing battery degradation behavior accurately.

---

## 12. Methodology Summary

The complete methodology can be summarized as:

```text
Battery Data Acquisition
        ↓
Data Preprocessing
        ↓
Energy and Units Calculation
        ↓
Charge Cycle Identification
        ↓
Window-Based SOH Calculation
        ↓
Feature Selection
        ↓
XGBoost / LightGBM Model Training
        ↓
Model Evaluation
        ↓
Visualization and Interpretation
```

This workflow combines battery diagnostics, machine learning, and predictive maintenance principles for EV lithium-ion battery health estimation.

---

## Code Availability

This public repository documents the methodology and research workflow only.

The full implementation code, notebooks, and experiment files are not publicly included in order to protect project integrity, dataset handling, and collaborative research work.
