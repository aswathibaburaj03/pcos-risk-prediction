# 🩺 Predicting PCOS Risk Before It's Too Late

> A statistical and machine learning pipeline for early detection of Polycystic Ovarian Syndrome (PCOS) — because early detection shouldn't depend on late diagnosis.

# 🎯 The Problem

PCOS affects roughly **1 in 5 young women**, yet it's frequently diagnosed late — often after symptoms have already progressed. Early risk prediction could change that. This project asks a simple question: can statistical modeling and machine learning flag risk earlier, using data we already collect?

# 📊 The Approach

This project combines two data sources for a more complete picture:
- **Clinical dataset** (n = 2,541) — merged from multiple secondary sources
- **Primary community survey** (n = 303) — real-world data collected specifically for this research

Across **8 chapters and 33 statistical methods**, the analysis spans everything from foundational hypothesis testing to predictive machine learning models.

# 🔬 Methods Used

- Descriptive & inferential statistics, Logistic Regression, LASSO
- Seven classification models compared: Gradient Boosting, Random Forest, KNN, SVM, Naive Bayes, Decision Tree, Logistic Regression
- Permutation feature importance for model interpretation
- Full pipeline built and executed in **Python** via Google Colaboratory

# 📈 Key Findings

- **Follicle count emerged as the single strongest predictor of PCOS risk** — by a wide margin (8x more influential than the next variable), followed by weight gain, hair growth, AMH levels, and skin darkening, supporting a practical, low-cost, tiered community screening approach.
- **Gradient Boosting was the best-performing model**, achieving 98.29% accuracy, an AUC-ROC of 0.9997, 97.02% sensitivity, and 98.88% specificity — outperforming six other classification models tested.

# 🎓 Background

This project was completed as part of an MSc dissertation in Applied Statistics & Data Analytics, University of Kerala.

---
*Feedback and suggestions welcome — feel free to open an issue or reach out.*
