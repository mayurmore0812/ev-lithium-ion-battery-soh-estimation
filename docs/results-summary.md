# Results Summary

## 1. Overview

This document summarizes the model performance and analytical findings from the EV lithium-ion battery State of Health estimation project.

The project evaluated battery SOH prediction using machine learning models, with a focus on:

* XGBoost-based SOH prediction during the final year project stage
* LightGBM-based SOH estimation during the research paper stage
* Regression-based performance evaluation
* Visual comparison of actual and predicted SOH
* Charge cycle-based battery degradation trend analysis

---

## 2. Evaluation Metrics

The models were evaluated using standard regression metrics.

| Metric              | Meaning                                                                   |
| ------------------- | ------------------------------------------------------------------------- |
| Mean Squared Error  | Measures the average squared difference between actual and predicted SOH  |
| Mean Absolute Error | Measures the average absolute difference between actual and predicted SOH |
| R² Score            | Measures how much variance in actual SOH is explained by the model        |

A lower MSE and MAE indicate smaller prediction errors.
A higher R² score indicates better model fit.

---

## 3. XGBoost Model Results

The final year project used XGBoost for SOH prediction.

The final reported model performance was:

| Metric              | Result |
| ------------------- | -----: |
| Mean Squared Error  | 1.8877 |
| Mean Absolute Error | 1.0183 |
| R² Score            | 0.9072 |

These results indicate that the XGBoost model was able to estimate battery SOH with strong predictive performance.

---

## 4. LightGBM Model Results

The research paper extended the project using LightGBM.

The reported LightGBM model performance was:

| Metric              | Result |
| ------------------- | -----: |
| Mean Squared Error  |  1.894 |
| Mean Absolute Error |  1.016 |
| R² Score            | 0.9069 |

The R² score of 0.9069 indicates that the LightGBM model explained approximately **90.69% of the variance** in SOH values.

---

## 5. Actual SOH vs Predicted SOH

The project compared actual SOH values with predicted SOH values to evaluate model accuracy.

The actual vs predicted SOH analysis showed that the model predictions generally followed the actual SOH trend. Close alignment between actual and predicted values indicates that the model captured key degradation patterns in the battery data.


<img width="400" height="200" alt="actual_soh-vs-predicted_soh" src="https://github.com/user-attachments/assets/26ba0603-d62e-487f-9568-737ccfb4a92b" />

Actual SOH vs Predicted SOH

This plot compares the actual SOH values with predicted SOH values and helps evaluate model prediction accuracy.


This comparison was useful for identifying:

* Prediction accuracy
* Outlier behavior
* Model reliability
* Cases where battery behavior was difficult to predict

---

## 6. Correlation Analysis

Correlation analysis was used to understand relationships between battery parameters and SOH.

The analysis showed that battery parameters such as State of Charge, pack voltage, cell voltage, capacity, charge cycle, and calculated energy-related features were important for understanding battery health behavior.

Charge cycle showed a strong relationship with SOH degradation, which supports the expected behavior that battery health reduces as charge cycles increase.

---

## 7. Charge Cycle vs SOH Trend

Charge cycle trend analysis was used to observe how battery health changed over repeated charging cycles.

The model output showed that predicted SOH followed the decreasing trend of actual SOH over charge cycles. This is important because a useful SOH prediction model should not only predict isolated values but also follow long-term battery degradation behavior.


<img width="300" height="200" alt="charge-cycle-vs-actual_and_predicted" src="https://github.com/user-attachments/assets/c679b09c-0bd6-4d69-9a2d-41b081ec14cb" />

Actual SOH vs Predicted SOH Degradation pattern

This visualization shows how actual and predicted SOH change over battery charge cycles, helping interpret battery degradation behavior.


This analysis supports the use of machine learning for predictive maintenance and battery health monitoring.

---

## 8. Polynomial Trend Analysis

Polynomial regression curves were used to smooth and interpret actual and predicted SOH trends.

This helped visualize the overall degradation pattern and compare whether the predicted SOH curve followed the actual SOH curve over time.

<img width="300" height="200" alt="polynomial_regression _curve_actual-vs-predicted" src="https://github.com/user-attachments/assets/792a2063-be4f-4de1-8d84-5c1adef3da4a" />

Polynomial Trend Curve

This curve provides a smoothed representation of battery degradation trends over charge cycles.


The trend analysis supported the conclusion that the model captured the general degradation trajectory of lithium-ion batteries.

---

## 9. Key Findings

The major findings from this project were:

* Machine learning can effectively estimate EV lithium-ion battery SOH from charging data.
* Window-based SOH calculation provides a structured way to analyze battery health across SOC intervals.
* XGBoost and LightGBM both showed strong performance on structured battery datasets.
* Charge cycle information is highly important for understanding battery degradation.
* The predicted SOH trend closely followed actual SOH behavior.
* The LightGBM model achieved an R² score of 0.9069.
* The XGBoost model achieved an R² score of 0.9072.

---

## 10. Interpretation

The results demonstrate that gradient boosting models can be effective for battery SOH estimation when supported by proper preprocessing, feature selection, and domain-specific SOH calculation.

The project also shows the importance of combining:

* Battery domain knowledge
* Data preprocessing
* Feature engineering
* Regression modeling
* Visual performance analysis

This makes the work relevant for battery diagnostics, predictive maintenance, electric vehicle reliability, and battery management systems.

---

## 11. Limitations

The public version of this project does not include full source code, notebooks, or raw datasets (dataset link is in README.md file).

Some limitations of the current documented version include:

* Raw dataset is not publicly included
* Full implementation pipeline is not shown
* Code-level reproducibility is restricted
* Results are presented as documented research outputs

---


## Code Availability

The full implementation code, notebooks, and experiment files are not publicly included in this repository.

This public repository is intended to summarize the research workflow, methodology, and results while protecting implementation details.
