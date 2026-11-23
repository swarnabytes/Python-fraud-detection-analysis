
# Credit Card Fraud Detection: EDA and Classification

Exploratory analysis and classification modelling on **284,807 credit card transactions** to understand how fraudulent transactions differ from genuine ones, and to build a baseline fraud classifier.

**Status:** EDA complete · Logistic Regression baseline complete · Model comparison in progress

---

## Business Problem

Card fraud causes direct financial loss, and fraud teams must find a very small number of bad transactions among millions of genuine ones. In this dataset fraud is only about 0.17% of transactions, so a model that predicts "genuine" every time looks 99.8% accurate but catches no fraud. This project therefore focuses on **understanding fraud patterns first** and evaluating models with **precision, recall and ROC-AUC** instead of accuracy.

## Dataset

- **Source:** [Kaggle: Credit Card Fraud Detection (ULB)](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- **Size:** 284,807 transactions, 31 columns
- **Columns:** `Time`, `Amount`, `Class` (0 = genuine, 1 = fraud), and `V1`–`V28` (anonymised PCA features)
- **Class balance:** about 0.17% fraud (highly imbalanced)

## Key Findings (EDA)

- **Fraud is rare:** only about 0.17% of transactions are fraudulent, so accuracy alone is misleading.
- **Average amount is higher for fraud:** mean amount is **122.21 for fraud vs 88.29 for genuine** transactions.
- **Typical amount is lower for fraud:** median amount is **9.25 for fraud vs 22.00 for genuine**. Fraud mixes many very small transactions with a few large ones, which pull the mean up. This pattern is consistent with fraudsters testing a stolen card with small amounts before larger charges.
- **Correlation, time and V-feature analysis:** see the folders listed below for the full breakdown.

<!--
TO DO BEFORE PUBLISHING: save 2-3 charts from your notebooks into an `images/` folder,
then remove the comment markers around the lines below.

![Fraud vs genuine amount distribution](images/amount_distribution.png)
![Feature correlation with fraud](images/correlation.png)
![Fraud by time of day](images/time_analysis.png)
-->

## Modelling

| Step | Status |
|---|---|
| Train-test split + StandardScaler | Done |
| Logistic Regression (baseline) | Done |
| Handling class imbalance | In progress |
| Decision Tree and Random Forest | In progress |
| Evaluation: precision, recall, F1, confusion matrix, ROC-AUC | In progress |

<!--
TO DO: once finished, replace this comment with a results table from your notebook, for example:

| Model | Precision | Recall | F1 | ROC-AUC |
|---|---|---|---|---|
| Logistic Regression | ... | ... | ... | ... |
| Random Forest | ... | ... | ... | ... |

Then add 2-3 lines on which model you would pick and why (a fraud team usually cares most about recall,
balanced against false alarms).
-->

## Repository Structure

```
├── Basic_EDA/                      # dataset inspection, missing values, duplicates
├── Transaction_comparison/         # fraud vs genuine comparison
├── Transactional_amount_analysis/  # transaction amount patterns
├── V_columns_analysis/             # anonymised PCA feature analysis
├── correlation/                    # correlation analysis
├── time_analysis/                  # time-based patterns
├── Check_Outliers.py               # outlier checks
├── ml.ipynb                        # modelling notebook
├── fraud_analysis_report.pdf       # written summary report
├── requirements.txt
└── README.md
```

## How to Run

1. Clone the repository and install the libraries:
   ```bash
   pip install -r requirements.txt
   ```
2. Download `creditcard.csv` from the Kaggle link above and place it in the project folder (it is not included here because of its size).
3. Open the notebooks in Jupyter and run the cells from top to bottom.

## Tools

Python · Pandas · NumPy · Matplotlib · Seaborn · Scikit-learn · Jupyter Notebook

## Next Steps

- Finish class-imbalance handling and compare models on recall and ROC-AUC
- Add a short risk interpretation: what false positives and false negatives would cost a bank

## Author

**Swarna Choudhary**, aspiring Data Analyst
Delhi NCR, India
