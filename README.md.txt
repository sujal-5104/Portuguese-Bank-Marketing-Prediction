# Portuguese Bank Marketing Prediction

## Project Overview

This project uses Machine Learning to predict whether a customer will subscribe to a bank term deposit based on marketing campaign information.

The project uses the Portuguese Bank Marketing dataset and compares multiple classification algorithms to identify a suitable predictive model.

## Objectives

- Perform data cleaning and exploratory data analysis.
- Identify factors associated with term deposit subscriptions.
- Build a customer subscription prediction model.
- Compare multiple Machine Learning algorithms.
- Tune and evaluate the best-performing model.
- Provide data-driven marketing recommendations.

## Dataset

**Dataset:** Bank Marketing – UCI Machine Learning Repository

The cleaned dataset contains 41,176 records and 21 columns.

Target variable: `y`

- `yes`: Customer subscribed to a term deposit.
- `no`: Customer did not subscribe.

The dataset is imbalanced, with approximately 88.73% non-subscribers and 11.27% subscribers.

Dataset source: https://archive.ics.uci.edu/dataset/222/bank+marketing

## Technologies Used

- Python
- Jupyter Notebook
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn
- Joblib

## Machine Learning Models

The following classification models were compared:

1. Logistic Regression
2. Decision Tree
3. Random Forest
4. Gradient Boosting
5. Extra Trees
6. HistGradientBoosting

HistGradientBoosting achieved the highest cross-validation PR-AUC among the initial models and was selected for hyperparameter tuning.

## Final Model Performance

The tuned HistGradientBoosting model achieved the following test results at the default 0.50 classification threshold:

| Metric | Score |
|---|---:|
| Accuracy | 90.06% |
| Precision | 66.67% |
| Recall | 23.49% |
| F1 Score | 34.74% |
| ROC-AUC | 81.39% |
| PR-AUC | 49.33% |

The classification threshold was also investigated to understand the trade-off between precision and recall.

## Important Features

Permutation importance identified these leading predictive features:

- Number of employees (`nr.employed`)
- Euribor 3-month rate (`euribor3m`)
- Contact communication type (`contact`)
- Consumer price index (`cons.price.idx`)
- Last contact month (`month`)
- Consumer confidence index (`cons.conf.idx`)
- Number of campaign contacts (`campaign`)

These are predictive associations and should not be interpreted as causal relationships.

## Business Recommendations

- Prioritize customers based on predicted subscription probability.
- Use previous campaign outcomes to guide future targeting.
- Evaluate campaign timing and communication channels.
- Avoid excessive repeated contact with customers.
- Test marketing strategies through controlled campaigns.
- Monitor precision and recall as business priorities change.

## Important Modeling Consideration

The `duration` variable was excluded from the production prediction model because call duration is only known after the call. Using it for a pre-call prediction would introduce data leakage.

## Project Structure

```text
Portuguese-Bank-Marketing-Prediction/
│
├── PRCP_1000_PortugueseBank.ipynb
├── README.md
├── .gitignore
│
└── models/
    └── portuguese_bank_final_model.pkl
```

## How to Run

1. Clone this repository.
2. Install the required Python libraries.
3. Download the Bank Marketing dataset from the UCI repository.
4. Place the dataset at the path expected by the notebook, or update the dataset path in the notebook.
5. Open `PRCP_1000_PortugueseBank.ipynb` in Jupyter Notebook.
6. Run the notebook cells from beginning to end.

Install the main dependencies:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib jupyter
```

## Author

**Sujal Padhiyar**

Machine Learning Project – PRCP-1000

## Disclaimer

This project is for educational and analytical purposes. Predictions should support, not replace, business judgment.