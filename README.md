# Uplift Modeling for Targeted Marketing Campaigns

## 📄 Project Summary

This project focuses on building uplift models to optimize marketing campaign targeting. Using the Criteo Uplift Modeling Dataset, we predict the **incremental impact** of a treatment (advertisement) on user conversions, enabling precise targeting to maximize ROI.

---

## 💡 Business Problem

Traditional predictive models estimate the likelihood of conversion, but marketers care about **incremental impact**: *"Will this user convert **because** of the ad?"*

Uplift modeling answers this by estimating the **causal impact** of a treatment:

> Uplift(x) = P(convert | treated, x) - P(convert | control, x)

This enables data-driven targeting strategies that:

* Reduce wasted marketing spend
* Avoid harming already-likely converters
* Improve conversion lift and ROI

---

## 🔬 Dataset Overview

* **Source**: [Criteo Uplift Modeling Challenge](https://www.criteo.com/blog/uplift-modeling/)
* **Rows**: 140K+ users
* **Columns**:

  * `treatment`: Binary flag (1 = shown ad)
  * `conversion`: Binary flag (1 = converted)
  * `features`: 11 anonymized numerical features (I1 to I11)

---

## 🎓 Methodology

### Step 1: Data Preprocessing

* Converted treatment and conversion columns to binary labels
* Created uplift labels (0 = CN, 1 = CY, 2 = TN, 3 = TY)

### Step 2: Stratified Train/Test Split

* Used uplift labels to ensure balanced representation across:

  * Control + No Conversion
  * Control + Conversion
  * Treatment + No Conversion
  * Treatment + Conversion

### Step 3: Modeling Approaches

#### ✅ Two-Model Approach

* Train 2 separate classifiers:

  * One on treatment group
  * One on control group
* Uplift = P1(x) - P0(x)

#### ✅ Class Transformation Approach

* Convert labels:

  * Positive uplift: (1,1) and (0,0) ➞ 1
  * Negative uplift: (1,0) and (0,1) ➞ 0
* Train a single classifier

### Step 4: Evaluation

* Metrics:

  * **Qini Curve**
  * **Uplift Curve**
* Models Compared:

  * Logistic Regression (Two-Model & Class Trans.)
  * Random Forest (Two-Model & Class Trans.)

---

## 📊 Key Results & Insights

| Model               | Strategy     | Qini Score         | Business Insight            |
| ------------------- | ------------ | ------------------ | --------------------------- |
| Logistic Regression | Two-Model    | \~Best on baseline | Simple, explainable         |
| Random Forest       | Class Trans. | Best uplift gain   | Strong for complex patterns |

* Uplift curves showed **significant lift** in top deciles
* Clear business case for targeting top uplift segments

---

## 🚀 Actionable Recommendations

* Target only users in top uplift deciles to boost conversions
* Avoid sending ads to users with negative uplift (may backfire)
* Periodically retrain using latest treatment data

---

## 📁 Project Structure (GitHub Folder Governance)

```
├── data/                  # Raw and cleaned datasets (or scripts to load them)
├── notebooks/             # Jupyter notebooks for EDA, modeling, evaluation
├── aml/                   # Uplift models and training scripts (sklift, lightgbm)
├── docs/                  # Visuals, metrics, architecture diagram
├── images/                # Curves and visuals for README
├── utils/                 # Helper functions (e.g., metrics, stratified split)
├── requirements.txt       # Reproducibility
└── README.md              # Project overview and documentation
```

---

## 🤖 Tools & Libraries

* Python, Pandas, Scikit-learn
* scikit-uplift (`sklift`)
* Matplotlib / Seaborn
* Jupyter Notebooks

---

## 💼 Use Cases & Interview Relevance

* **Marketing Optimization**: Allocate budget to users with highest net lift
* **Causal Inference**: Understand true effect of interventions
* **Data Science Interviews**: Showcases modeling, experimentation, and business impact

---

## 🚫 Limitations & Next Steps

* Only numerical features used; adding demographics can improve lift
* No hyperparameter tuning; can boost performance
* Could try advanced meta-learners (S-, T-, X-Learners)
* Add Streamlit dashboard for stakeholder exploration

---

## 🌟 Author

Tanmay Patel
MS in Data Analytics | Uplift Modeling | Causal Inference | Marketing Data Science
