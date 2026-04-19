# Assignment-5
# Sovereign Risk Early Warning System (IMF Simulation)

An end-to-end machine learning pipeline designed to predict sovereign debt crises using macroeconomic indicators from the World Bank. This project simulates the decision-making process of an IMF economist under real-world resource constraints.

## 🚀 Project Overview
Developed a robust predictive model to identify national economic crises by processing **25+ macroeconomic indicators**. The system utilizes a Logistic Regression classifier optimized for high-dimensional data to provide actionable insights for policy intervention.

## 🛠️ Tech Stack
* **Data Source**: World Bank API (`wbgapi`)
* **Language**: Python
* **Key Libraries**: Pandas, Scikit-learn, Matplotlib, Seaborn
* **Algorithms**: 
  * **Lasso/Ridge Regression**: For feature selection and regularization.
  * **Logistic Regression**: For binary risk classification.
  * **Linear Probability Model (LPM)**: Baseline for bias/variance comparison.

## 📊 Project Phases & Key Findings

### Phase 1: Overcoming Overfitting
Demonstrated the failure of OLS in high-dimensional settings ($p/n \approx 0.125$). Implementing **Lasso Regression** successfully identified 14-21 significant predictors and significantly reduced the training-test $R^2$ gap.

### Phase 2: Crisis Classification
Compared LPM and Logistic models. The LPM produced invalid negative probabilities (min: -0.52), while **Logistic Regression** effectively constrained predictions to the $[0, 1]$ interval. The classifier achieved an **AUC of 0.96**.


### Phase 3: Operational Deployment
Simulated an IMF environment with a **5-mission capacity constraint**. Using **Precision-Recall curve** analysis, the decision threshold was optimized to **$\tau = 0.20$**, maximizing resource utilization while maintaining high sensitivity.


### Phase 4: Risk Dashboard
Created a visualization mapping predicted probabilities against actual GDP growth. This dashboard identifies "Intervention Zones," allowing for the precise allocation of emergency liquidity to countries with the highest risk scores.

## 📈 Final Results
* **Optimal Threshold**: 0.20
* **Classification Accuracy**: 0.945
* **Model Discriminatory Power**: AUC = 0.96
* **Policy Recommendation**: Adopt the 0.20 threshold to mitigate the high systemic cost of **False Negatives** (missed crises).
