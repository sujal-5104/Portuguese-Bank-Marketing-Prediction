# Portuguese Bank Marketing Prediction 📊

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Classification-orange)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-yellow?logo=scikitlearn)
![Status](https://img.shields.io/badge/Project-Completed-success)

## 📌 Project Overview

The Portuguese Bank Marketing Prediction project uses Machine Learning classification algorithms to predict whether a customer will subscribe to a bank term deposit following a marketing campaign.

The objective is to analyze customer and campaign-related information, identify important subscription patterns, compare multiple classification models, and recommend an effective predictive model.

## 🎯 Project Objectives

- Perform data cleaning and exploratory data analysis (EDA).
- Understand customer subscription patterns.
- Identify important factors influencing term deposit subscriptions.
- Build classification models to predict customer responses.
- Compare different Machine Learning algorithms.
- Perform cross-validation and hyperparameter tuning.
- Evaluate model performance using classification metrics.
- Provide actionable marketing recommendations.

## 📂 Dataset Information

**Dataset:** Portuguese Bank Marketing Dataset

**Source:** UCI Machine Learning Repository

https://archive.ics.uci.edu/dataset/222/bank+marketing

| Description | Value |
|---|---:|
| Total Records After Cleaning | 41,176 |
| Total Columns | 21 |
| Training Records | 32,940 |
| Testing Records | 8,236 |
| Target Variable | `y` |

### Target Variable

- `yes` – Customer subscribed to a term deposit.
- `no` – Customer did not subscribe.

### Target Distribution

| Customer Response | Count | Percentage |
|---|---:|---:|
| No | 36,537 | 88.73% |
| Yes | 4,639 | 11.27% |

The dataset is imbalanced, so precision, recall, F1-score, ROC-AUC, and PR-AUC were considered during model evaluation.

## 🛠️ Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib

## 🤖 Machine Learning Models

Six classification algorithms were implemented and compared:

1. Logistic Regression
2. Decision Tree Classifier
3. Random Forest Classifier
4. Gradient Boosting Classifier
5. Extra Trees Classifier
6. HistGradientBoosting Classifier

## 📊 Model Performance Comparison

Initial model comparison on the test dataset:

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC | PR-AUC |
|---|---:|---:|---:|---:|---:|---:|
| HistGradientBoosting | 90.08% | 66.57% | 24.03% | 35.31% | 81.46% | **49.47%** |
| Random Forest | 87.43% | 45.61% | 59.91% | 51.79% | 81.06% | 47.66% |
| Gradient Boosting | 89.81% | 65.08% | 20.69% | 31.40% | 80.38% | 47.57% |
| Extra Trees | 86.02% | 41.97% | 62.82% | 50.32% | 80.61% | 47.17% |
| Decision Tree | 84.34% | 37.97% | 61.53% | 46.96% | 77.69% | 44.86% |
| Logistic Regression | 83.04% | 35.93% | 64.55% | 46.17% | 80.01% | 44.60% |

## 🏆 Best Performing Model

**Selected Model: HistGradientBoosting Classifier**

HistGradientBoosting achieved the highest cross-validation PR-AUC among the initial candidate models and was selected for hyperparameter tuning.

### Hyperparameter Tuning

The following parameters were selected:

- `max_leaf_nodes`: 15
- `max_iter`: 150
- `learning_rate`: 0.03
- `l2_regularization`: 0.1

### Final Tuned Model Test Results

| Evaluation Metric | Score |
|---|---:|
| Accuracy | 90.06% |
| Precision | 66.67% |
| Recall | 23.49% |
| F1 Score | 34.74% |
| ROC-AUC | 81.39% |
| PR-AUC | 49.33% |

The classification threshold was also analyzed to understand the trade-off between precision and recall.

## 🔍 Important Features

Permutation feature importance identified the following leading predictive features:

1. Number of Employees (`nr.employed`)
2. Euribor 3-Month Rate (`euribor3m`)
3. Contact Communication Type (`contact`)
4. Consumer Price Index (`cons.price.idx`)
5. Last Contact Month (`month`)
6. Consumer Confidence Index (`cons.conf.idx`)
7. Number of Campaign Contacts (`campaign`)
8. Day of the Week (`day_of_week`)

These features indicate predictive associations and do not establish causal relationships.

## 💡 Business Recommendations

- Prioritize customers with higher predicted subscription probabilities.
- Analyze previous campaign outcomes before contacting customers again.
- Select suitable communication channels.
- Avoid excessive repeated calls to customers.
- Analyze campaign timing and seasonal patterns.
- Use controlled marketing experiments to evaluate campaign effectiveness.
- Monitor precision and recall to balance marketing costs and customer reach.

## ⚠️ Data Leakage Prevention

The `duration` feature was excluded from the predictive model because call duration is only available after a marketing call has taken place.

Including it would create data leakage for a prediction intended to be made before contacting the customer.

## 📁 Project Structure

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

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/sujal-5104/Portuguese-Bank-Marketing-Prediction.git
```

### 2. Navigate to the project folder

```bash
cd Portuguese-Bank-Marketing-Prediction
```

### 3. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib jupyter
```

### 4. Download the dataset

Download the Bank Marketing dataset from the UCI Machine Learning Repository.

Place `bank-additional-full.csv` in the expected dataset folder or update the dataset path in the notebook.

### 5. Open Jupyter Notebook

```bash
jupyter notebook
```

Open `PRCP_1000_PortugueseBank.ipynb` and run the cells sequentially.

## 💾 Saved Model

The final trained model and its selected classification threshold are saved in:

```text
models/portuguese_bank_final_model.pkl
```

The model package includes:
- Trained machine learning pipeline
- Selected prediction threshold
- Input feature names
- Target label mapping

## 📚 Key Learning Outcomes

- Exploratory Data Analysis
- Handling categorical and numerical variables
- Feature engineering
- Handling imbalanced classification datasets
- Machine Learning model comparison
- Cross-validation
- Hyperparameter optimization
- Classification evaluation
- Permutation feature importance
- Model persistence using Joblib

## 👨‍💻 Author

**Sujal Padhiyar**

GitHub: https://github.com/sujal-5104

## 📌 Project Information

- **Project ID:** PRCP-1000
- **Domain:** Data Science / Machine Learning
- **Project Type:** Classification
- **Status:** Completed

## ⚖️ Disclaimer

This project is developed for educational and analytical purposes. Model predictions should support business decisions rather than replace human judgment.
