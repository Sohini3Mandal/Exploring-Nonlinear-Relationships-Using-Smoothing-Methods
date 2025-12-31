# Exploring Nonlinear Relationships Using Smoothing Methods


**Course:** Advanced Regression Techniques (MDTS4313)

**Programme:** M.Sc. Data Science (Semester III)
**Author:** Sohini Mandal

**Roll No:** 444

**Institution:** St. Xavier’s College (Autonomous), Kolkata

---

## Repository Contents

```
📁 Exploring-Nonlinear-Relationships-Smoothing
│
├── xploring Nonlinear Relationships Using Smoothing Methods (Notebook).ipynb
├── Exploring Nonlinear Relationships Using Smoothing Methods (Report).pdf
└── README.md
```

---

## Project Description

This project explores the nonlinear relationship between fish length and fish weight using **nonparametric smoothing methods**.
The analysis focuses on modeling curvature in the data without assuming a fixed functional form and comparing the predictive performance of different smoothers.

---

## Dataset

* **Dataset:** Fish Market
* **Source:** Kaggle
* **Sample Size:** 124 observations
* **Independent Variable (X):** Diagonal length of fish (`Length2`, cm)
* **Dependent Variable (Y):** Fish weight (grams)

---

## Data Preprocessing

* No missing values were found
* Outliers in weight were detected and removed using the **IQR method (1.5 × IQR)**
* After cleaning, the data showed a clear upward nonlinear pattern between length and weight

---

## Methods Implemented

All methods were tuned using **10-fold cross-validation**:

* **K-Nearest Neighbors (KNN) Smoothing** – tuned using number of neighbors (k)
* **Gaussian Kernel Regression** – tuned using bandwidth (h)
* **LOWESS** – tuned using smoothing fraction (frac)

Both **MAE** and **MSE** were used for validation.

---

## Results Summary

| Method                     | Best Hyperparameter | Test MSE      |
| -------------------------- | ------------------- | ------------- |
| KNN Smoother               | k = 6               | 15396.136     |
| Gaussian Kernel Regression | h = 3.816           | **13510.363** |
| LOWESS                     | frac = 0.168        | 21008.723     |

Gaussian Kernel Regression achieved the lowest test error.

---

## Visual Comparison

The fitted curves from all three best models were plotted on the same scatterplot:

* **LOWESS** produced the smoothest visual curve
* **KNN** showed step-like local behavior
* **Kernel Regression** balanced smoothness and accuracy

---

## Conclusion

Among the smoothing methods considered, **Gaussian Kernel Regression** performed best on unseen data.
LOWESS provided a smoother visual fit but higher test error, while KNN showed greater sensitivity to local fluctuations.
The results emphasize the importance of **hyperparameter tuning** in nonparametric regression.

---

## Tools Used

Python · NumPy · Pandas · Scikit-learn · Statsmodels · Matplotlib

---
