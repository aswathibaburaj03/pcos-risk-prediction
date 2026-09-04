# Statistical Modelling and Machine Learning Approaches for Early Risk Prediction of PCOS Among Young Women

MSc Statistics dissertation (University of Kerala, Kariavattom) combining a secondary clinical dataset and a primary community survey to predict and characterise PCOS risk among young women in Kerala, using 33 statistical and machine learning methods across 14 objectives.

📄 **Full dissertation:** [`ASWATHIBABURAJAN_PCOS_FINAL_DRAFT.pdf`](./ASWATHIBABURAJAN_PCOS_FINAL_DRAFT.pdf)

## Overview

The study combines two data sources:

- **Secondary clinical data** — an anonymised dataset of 2,541 patients (45 variables) merged from hospital records across Kerala, used for statistical modelling and machine learning
- **Primary survey data** — a 31-question structured survey of 303 young women (aged 15–35) across Kerala, used to assess PCOS awareness, symptom prevalence, and health-seeking behaviour

### Secondary Analysis

- Compared clinical, hormonal, demographic, and lifestyle characteristics between PCOS and non-PCOS groups
- Assessed multicollinearity (VIF, correlation matrix) and applied PCA for dimensionality reduction
- Fit and interpreted a binary logistic regression model (odds ratios, 95% CIs) and a LASSO-penalised logistic regression for feature selection
- Trained and compared 7 supervised ML classifiers — Decision Tree, Random Forest, KNN, Naive Bayes, SVM, and Gradient Boosting — using stratified, patient-grouped 5-fold cross-validation
- Handled class imbalance via cost-sensitive class weighting
- Interpreted the best model with permutation feature importance
- Applied Factor Analysis, Linear Discriminant Analysis, and K-Means clustering to identify clinical subgroups

### Primary Survey Analysis

- Profiled demographics, symptom prevalence, lifestyle patterns, and health-seeking behaviour
- Quantified PCOS awareness and its association with demographic factors (Chi-squared tests)
- Constructed and validated an 8-symptom PCOS risk score via ROC analysis
- Tested associations between risk score, lifestyle factors, and awareness (ANOVA, Kruskal-Wallis, Spearman correlation, logistic regression)
- Cross-validated symptom prevalence against the secondary dataset and quantified the community-level diagnostic gap

## Key Findings

**Secondary data — model performance (ranked by AUC, single test set):**

| Rank | Model | Accuracy | AUC-ROC | Sensitivity | Specificity | F1 |
|---|---|---|---|---|---|---|
| 1 | Gradient Boosting | 98.29% | 0.9997 | 97.02% | 98.88% | 0.9731 |
| 2 | Random Forest | 94.11% | 0.9887 | 86.90% | 97.49% | 0.9040 |
| 3 | KNN | 97.72% | 0.9837 | 97.02% | 98.04% | 0.9645 |
| 4 | SVM | 93.54% | 0.9676 | 86.90% | 96.65% | 0.8957 |
| 5 | Logistic Regression | 89.98% | 0.9535 | 77.07% | 95.74% | 0.8259 |
| 6 | Naive Bayes | 84.98% | 0.9314 | 79.17% | 87.71% | 0.7710 |
| 7 | Decision Tree | 84.98% | 0.8976 | 85.71% | 84.64% | 0.7847 |

- **Gradient Boosting** was the strongest model (AUC 0.9997, mean CV AUC 0.9892), with **Follicle Number (L)** the dominant predictor by permutation importance — its removal alone cost ~8x more AUC than the next-ranked variable (weight gain)
- Even the weakest model (Decision Tree, AUC 0.8976) exceeded the 0.80 threshold for good clinical discrimination, confirming genuine predictive signal in the 22-variable predictor set
- Logistic regression and LASSO remained clinically valuable for their interpretable odds ratios despite lower predictive accuracy than the ensemble models

**Primary survey — the diagnostic gap:**

- **52.1%** of surveyed young women had never been tested for PCOS
- **49.8%** fell into the moderate-to-very-high PCOS symptom risk category (risk score ≥ 3 of 8)
- An 8-symptom self-reported risk score achieved **AUC 0.8133** for identifying at-risk women without lab tests
- Among never-tested respondents, only 38.0% were fully aware of PCOS vs. 50.2% in the overall sample — the least-informed women are also the least likely to have been screened

## Dissertation Structure

| Chapter | Contents |
|---|---|
| 1 | Introduction — background, significance, objectives, scope |
| 2 | Literature Review — epidemiology, diagnostic criteria, prior statistical/ML approaches, PMOS renaming |
| 3 | Data and Methodology — data sources, cleaning, feature engineering, model specifications |
| 4 | Exploratory Data Analysis — secondary clinical dataset and primary survey dataset |
| 5 | Statistical Modelling Results — VIF, logistic regression, LASSO, ROC analysis |
| 6 | Machine Learning Results — 7-model comparison, cross-validation, permutation importance |
| 7 | Discussion — clinical interpretation, community validation, PMOS alignment, limitations |
| 8 | Conclusion |

## Tools

- **Python 3.12** — run in Google Colaboratory
- **Key libraries:** `pandas`, `numpy`, `scikit-learn`, `statsmodels`, `factor_analyzer`, `matplotlib`, `seaborn`
- **Key techniques:** logistic regression with 95% CIs, LASSO-penalised regression, VIF/multicollinearity diagnostics, PCA, Decision Tree / Random Forest / KNN / Naive Bayes / SVM / Gradient Boosting classifiers, cost-sensitive class weighting, stratified patient-grouped k-fold cross-validation, ROC-AUC analysis, permutation feature importance, Factor Analysis, Linear Discriminant Analysis, K-Means clustering, non-parametric hypothesis testing (Mann-Whitney U, Kruskal-Wallis, Chi-squared, two-proportion Z-test), Spearman correlation

> **Note:** this repository currently contains the final dissertation document only. The underlying clinical and survey datasets, and the analysis notebooks, are not included here due to data confidentiality — get in touch if you'd like more information.

## Author

**Aswathi Babu Rajan** — MSc Applied Statistics & Data Analytics, University of Kerala.
aswathibaburaj03@gmail.com
