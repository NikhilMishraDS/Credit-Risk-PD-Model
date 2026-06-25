# Credit Risk & Probability of Default (PD) Model

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-2.0-orange?logo=xgboost)
![SHAP](https://img.shields.io/badge/XAI-SHAP-blueviolet)
![Basel III](https://img.shields.io/badge/Basel%20III-Compliant-green)
![IFRS 9](https://img.shields.io/badge/IFRS%209-Ready-green)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

> An end-to-end machine learning framework for estimating the **Probability of Default (PD)** of loan applicants — aligned with **Basel III IRB** and **IFRS 9** regulatory standards, with full **SHAP-based model explainability**.

---

## 🏦 Business Context

Financial institutions lose billions annually to credit defaults. Traditional credit scoring methods often fail to capture complex, non-linear risk signals embedded in borrower behavior. This project addresses that gap with:

- **Predictive accuracy** — XGBoost outperforms traditional scorecards
- **Regulatory compliance** — framework aligned with Basel III and IFRS 9 ECL requirements
- **Explainability** — SHAP values meet the "right to explanation" requirement for credit decisions
- **Risk segmentation** — borrowers bucketed into actionable risk tiers for underwriting

---

## 📊 Results

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---|---|---|---|---|
| Logistic Regression (Baseline) | ~85% | ~80% | ~75% | ~77% | ~0.88 |
| **XGBoost (Final Model)** | **~92%** | **~89%** | **~86%** | **~87%** | **~0.96** |

> XGBoost achieved **~0.96 ROC-AUC**, indicating excellent discriminatory power for separating default vs. non-default borrowers.

---

## 🛠️ Tech Stack

| Layer | Tools |
|---|---|
| Language | Python 3.10+ |
| ML Models | Scikit-learn, XGBoost |
| Explainability | SHAP (SHapley Additive exPlanations) |
| EDA & Visualization | Pandas, NumPy, Matplotlib, Seaborn |
| Preprocessing | Scikit-learn Pipelines, ColumnTransformer |
| Regulatory Alignment | Basel III IRB Approach, IFRS 9 ECL |
| Notebook | Jupyter |

---

## 📁 Project Structure

```
credit-pd-model/
├── Credit_Probability_of_Default_PD_Model.ipynb   # Main notebook
├── src/
│   ├── preprocessing.py        # Feature engineering & pipelines
│   ├── model.py                # Model training & evaluation
│   └── risk_segmentation.py    # PD → Risk band conversion
├── tests/
│   └── test_preprocessing.py   # Unit tests
├── docs/
│   └── architecture.md         # Model architecture & design decisions
├── requirements.txt
├── .env.example
└── README.md
```

---

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/credit-pd-model.git
cd credit-pd-model

# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook Credit_Probability_of_Default_PD_Model.ipynb
```

---

## 🔬 Methodology

```
Data Ingestion → EDA → Feature Engineering → Preprocessing Pipeline
      ↓
Logistic Regression (Baseline) → XGBoost (Final Model)
      ↓
SHAP Explainability → PD Scores → Risk Segmentation → Portfolio Dashboard
```

### Key Feature Engineering
| Feature | Formula | Risk Signal |
|---|---|---|
| Loan-to-Income Ratio (LTI) | `loan_amnt / person_income` | Affordability stress |
| Income Per Year Employed | `income / (emp_length + 1)` | Employment stability |
| Credit History Age Ratio | `cred_hist_length / (age + 1)` | Credit maturity |
| High-Risk Grade Flag | `1 if grade in [D,E,F,G]` | Grade-based risk |

### Risk Segmentation
| PD Score | Risk Band | Lending Action |
|---|---|---|
| 0–5% | Very Low Risk | Auto-approve |
| 5–15% | Low Risk | Standard underwriting |
| 15–30% | Moderate Risk | Enhanced review |
| 30–50% | High Risk | Collateral required |
| 50–100% | Very High Risk | Decline / Refer |

---

## 🔍 Explainability (SHAP)

SHAP (SHapley Additive exPlanations) is used to explain individual predictions — a key requirement for **SR 11-7 model risk governance** and **GDPR Article 22** (right to explanation).

Top drivers of default identified by SHAP:
1. Loan-to-income ratio
2. Interest rate
3. Loan grade
4. Prior default history (`cb_person_default_on_file`)
5. Credit history length

---

## 📋 Regulatory Alignment

| Standard | Application |
|---|---|
| **Basel III IRB** | PD estimation for Risk-Weighted Asset (RWA) calculation |
| **IFRS 9 ECL** | Stage 1/2/3 classification using PD thresholds |
| **SR 11-7** | Model documentation, validation, and explainability |

---

## 🗺️ Roadmap

- [ ] Loss Given Default (LGD) model
- [ ] Exposure at Default (EAD) model
- [ ] Expected Credit Loss (ECL = PD × LGD × EAD)
- [ ] Stress testing under macroeconomic scenarios
- [ ] REST API deployment (FastAPI)
- [ ] Model monitoring dashboard (Evidently AI)

---

## 👤 Author

**[Nikhil Kumar Mishras]**
📧 [mishranikhil9104@gmail.com]
🔗 [LinkedIn](www.linkedin.com/in/nikhil-mishra-927650288)
💼 Targeting: Credit Risk | Quantitative Finance | ML in Banking

---

