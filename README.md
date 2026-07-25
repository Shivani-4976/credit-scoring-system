<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&height=250&color=gradient&text=CreditSense%20AI&fontSize=55&fontColor=ffffff&animation=fadeIn&desc=Credit%20Scoring%20and%20Loan%20Default%20Prediction%20System&descAlignY=60&descSize=18" width="100%"/>

### Production-ready Machine Learning Pipeline
### from Data Preprocessing to Deployment

<br/>

</div>

<br/>

## 📖 Introduction

Lending decisions come down to one high-stakes question: *will this applicant repay the loan?* **CreditSense AI** frames this as a supervised classification problem and builds a complete pipeline around it — from a raw, imperfect real-world dataset to a deployed decision-support tool.

- Manual credit assessment is slow and inconsistent at scale; a trained classifier flags risk instantly and consistently.
- Surfacing *which* factors drive a prediction (feature importance) gives a transparent, explainable basis for a decision instead of a black box.
- This mirrors the probability-of-default models banks, microfinance institutions, and fintech lenders use before extending a loan.

---

## 🌐 Live Demo

<div align="center">

[![Open App](https://img.shields.io/badge/🚀%20Open%20App-Streamlit%20Cloud-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://credit-scoring-system-kgsxmwuhqibn6mcqvbw7rz.streamlit.app/)
[![View Repo](https://img.shields.io/badge/📂%20View%20Repository-GitHub-181717?style=for-the-badge&logo=github&logoColor=white)]()

</div>

---

## 🖼️ Project Preview

<div align="center">

**Dashboard Preview**

<img src="images/dashboard_preview.gif" width="90%"/>

<br/><br/>

| Prediction Page | Model Analytics |
|:---:|:---:|
| <img src="C/redit_Scoring_Systemimages/prdiction_page.png" width="100%"/> | <img src="Credit_Scoring_System/images/model_analytics.png" width="100%"/> |

| Feature Insights | Dataset Overview |
|:---:|:---:|
| <img src="Credit_Scoring_System/images/feature_insights.png" width="100%"/> | <img src="Credit_Scoring_System/images/dataset_overview.png" width="100%"/> |

</div>

---

## ✨ Key Features

| | | |
|:---|:---|:---|
| ✔ **Data Cleaning** — median imputation | ✔ **Feature Engineering** — Label & One-Hot Encoding | ✔ **Multi-Model Training** — LR, Decision Tree, Random Forest |
| ✔ **Model Comparison** — accuracy benchmarked | ✔ **Feature Importance** — per-model charts | ✔ **Confusion Matrix Evaluation** |
| ✔ **Real-Time Prediction** — instant verdict | ✔ **Risk Level Badges** — Low / Medium / High | ✔ **PDF Report Generation** |
| ✔ **Interactive Streamlit Dashboard** — 4 tabs | ✔ **Model Persistence** — Joblib | ✔ **Dataset Overview Tab** — live stats & charts |

---

## 🔄 Project Workflow

```mermaid
flowchart TD
    A[Raw Dataset<br/>32,581 records]:::data --> B[Data Cleaning<br/>Median Imputation]:::prep
    B --> C[Exploratory Data Analysis]:::prep
    C --> D[Feature Engineering<br/>Label + One-Hot Encoding]:::prep
    D --> E[Train / Test Split<br/>80% / 20%]:::prep
    E --> F[Model Training]:::model
    F --> F1[Logistic Regression]:::model
    F --> F2[Decision Tree]:::model
    F --> F3[Random Forest]:::model
    F1 --> G[Evaluation<br/>Accuracy + Confusion Matrix]:::eval
    F2 --> G
    F3 --> G
    G --> H[Model Persistence<br/>Joblib .pkl]:::deploy
    H --> I[Streamlit Dashboard<br/>Prediction + PDF Report]:::deploy

    classDef data fill:#0D1F3C,stroke:#00D4FF,color:#E8F4FD;
    classDef prep fill:#0A1628,stroke:#7B61FF,color:#E8F4FD;
    classDef model fill:#0A1628,stroke:#00D4FF,color:#E8F4FD;
    classDef eval fill:#0A1628,stroke:#FFA000,color:#E8F4FD;
    classDef deploy fill:#0A1628,stroke:#00FF88,color:#E8F4FD;
```

---

## 📂 Folder Structure

```
credit-scoring-system/
├── 📄 README.md
└── 📂 Credit_Scoring_System/
    ├── 📄 app.py                     # Streamlit dashboard (CreditSense AI)
    ├── 📄 credit_score_model.ipynb   # Cleaning, EDA, training & evaluation
    ├── 📄 requirements.txt
    ├── 📂 dataset/
    │   └── 📄 credit_risk_dataset.csv
    ├── 📂 model/
    │   └── 📄 credit_score.pkl
    └── 📂 images/
        ├── 🖼️ dataset_overview.png
        ├── 🖼️ distribution.png
        ├── 🖼️ heatmap.png
        ├── 🖼️ confusion_matrix.png
        ├── 🖼️ feature_insights.png
        ├── 🖼️ gui1.png
        ├── 🖼️ model_analytics.png
        ├── 🖼️ prdiction_page.png
        └── 🎞️ dashboard_preview.gif
```

---

## 📊 Dataset

| Detail | Value |
|---|---|
| **Source file** | `dataset/credit_risk_dataset.csv` |
| **Records** | 32,581 loan applicants |
| **Columns** | 12 (11 features + 1 target) |
| **Target column** | `loan_status` — 0 = No Default, 1 = Default |
| **Class balance** | 78.2% No Default / 21.8% Default |
| **Missing values** | `person_emp_length`: 895 · `loan_int_rate`: 3,116 |
| **Preprocessing** | Median imputation → Label Encoding (`person_home_ownership`) → Binary mapping (`cb_person_default_on_file`) → One-Hot Encoding, drop-first (`loan_intent`, `loan_grade`) |

**Feature set:** `person_age` · `person_income` · `person_home_ownership` · `person_emp_length` · `loan_intent` · `loan_grade` · `loan_amnt` · `loan_int_rate` · `loan_percent_income` · `cb_person_default_on_file` · `cb_person_cred_hist_length`

---

## 🔍 Exploratory Data Analysis

- **Class imbalance:** ~78.2% no-default vs. ~21.8% default, confirmed via `sns.countplot`.
- **Missing data:** real missingness in `person_emp_length` (895 rows) and `loan_int_rate` (3,116 rows), resolved with median imputation.
- **Correlation heatmap:** generated across numeric features to spot relationships before modeling.
- **Distribution plots:** produced for numeric fields to check spread and skew ahead of encoding.

<div align="center">

<table>
<tr>
<th align="center">📊 Distribution Analysis</th>
<th align="center">🔥 Correlation Heatmap</th>
</tr>

<tr>
<td align="center">
<img src="Credit_Scoring_System/images/distribution.png" width="380">
</td>

<td align="center">
<img src="Credit_Scoring_System/images/heatmap.png" width="380">
</td>
</tr>
</table>

</div>
---

## 🧪 Machine Learning Pipeline

`Data Collection → Cleaning → Encoding → Split (80/20) → Training (LR, Decision Tree, Random Forest) → Evaluation → Deployment`

> No explicit feature scaling step exists in the notebook — all three models, including Logistic Regression, train on unscaled features (see [Future Improvements](#-future-improvements)).

---

## 🤖 Models Used

| Model | Accuracy | Status |
|---|---|:---:|
| Logistic Regression | 83.12% | ✅ |
| Decision Tree Classifier | 89.09% | ✅ |
| **Random Forest Classifier (100 trees)** | **93.34%** | 🏆 Best |

The Random Forest ensemble outperforms both the linear model and the single tree, consistent with default risk depending on non-linear feature interactions (e.g. loan-to-income ratio combined with loan grade).

> **Deployed artifact note:** `model/credit_score.pkl` — the file actually shipped with the app — is a `DecisionTreeClassifier` (89.09%), not the higher-scoring Random Forest. Flagged under Future Improvements.

---

## 📈 Performance Metrics

Accuracy for all three models and a confusion matrix for Random Forest are the only metrics present in the notebook's saved outputs — reported exactly as produced. Precision, recall, F1-score, and ROC-AUC were not saved in the notebook, so they are left out rather than estimated.

![Confusion Matrix](Credit_Scoring_System/images/confusion_matrix.png)

---

## 🔬 Feature Importance

The app computes importance live per selected model — `feature_importances_` for tree-based models, coefficient magnitude for Logistic Regression — plus a default-rate-by-loan-grade chart.

![Feature Insights](Credit_Scoring_System/images/feature_insights.png)

**Loan grade**, **loan-to-income ratio**, and **interest rate** consistently emerge as the strongest drivers of predicted default probability.

---

## 🛠️ Technology Stack

**Programming**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)

**Machine Learning**

![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Joblib](https://img.shields.io/badge/Joblib-Model%20Persistence-blue?style=flat-square)

**Visualization**

![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat-square&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=flat-square)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white)

**Deployment**

![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![ReportLab](https://img.shields.io/badge/ReportLab-PDF%20Generation-red?style=flat-square)

**Tools**

![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)

---

## 🚀 Installation Guide

```bash
# 1. Clone the repository
git clone https://github.com/rizwanahmed786508/credit-scoring-system.git
cd credit-scoring-system/Credit_Scoring_System

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the Streamlit app
streamlit run app.py
```

Streamlit opens automatically at `http://localhost:8501`.

---

## 📘 Usage Guide

1. **Prediction tab** — pick a model, enter applicant/loan details in the sidebar, click **Run Prediction** for an Approved/Rejected verdict, probability gauge, and risk badge (Low/Medium/High). Export a **PDF report** if needed.
2. **Model Analytics tab** — compare accuracy/ROC-AUC across models and view the confusion matrix.
3. **Feature Insights tab** — inspect feature importance and default rate by loan grade.
4. **Dataset Overview tab** — browse summary metrics, loan-purpose distribution, and sample records.

> For live-demo responsiveness, the deployed app trains all three models on a 3,000-row synthetic dataset mirroring the original schema. The displayed **accuracy** values are pinned to the real notebook results (83.12% / 89.09% / 93.34%); ROC-AUC and the confusion matrix reflect the synthetic-data run.

---

## 🔮 Future Improvements

- Re-save the deployed artifact from the actual best model (Random Forest), not the current Decision Tree pickle
- Report full precision, recall, F1-score, and ROC-AUC on the real dataset
- Add feature scaling for Logistic Regression
- SHAP-based explainability for individual predictions
- Hyperparameter tuning (GridSearchCV / Optuna)
- Docker containerization
- REST API exposure
- Cloud deployment beyond Streamlit Community Cloud
- Model monitoring and retraining pipeline
- CI/CD pipeline

---

## 📜 License

This project is developed for educational, research, and portfolio purposes.

---

## 👨‍💻 Author

<div align="center">

**Rizwan Ahmed**
Machine Learning Engineer · BS Software Engineering, Sukkur IBA University

*Inspired by real-world banking credit risk assessment workflows.*

<br/>

⭐ **If you found this project useful, consider giving it a star.**

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&height=100&color=gradient&section=footer" width="100%"/>

</div>
