# 🧠 Uplift Modeling on Criteo Dataset (Azure + Databricks)

## 🎯 Business Objective

Digital ad budgets are often wasted on users who would convert anyway. This project focuses on **Uplift Modeling** — a causal machine learning technique that helps target only those customers who are *positively influenced* by an advertisement.

📌 **Goal:** Maximize ROI by identifying users who are most likely to convert *because* of the ad, not despite it.

---

## 🧱 Project Architecture

```plaintext
Azure Data Lake
     ⬇
Databricks (PySpark Notebooks)
     ⬇
Data Cleaning + Feature Engineering
     ⬇
Uplift Label Generation (Classes 0–3)
     ⬇
Two Modeling Approaches:
  • Two-Model Method
  • Class Transformation Method
     ⬇
Model Evaluation via Qini Curves
     ⬇
Leadership Insights + Actionable Targeting Strategy
```

---

## ⚙️ Tech Stack

| Category               | Tools / Libraries                                                                                               |
| ---------------------- | ---------------------------------------------------------------------------------
| **Cloud Platform**     | Azure Data Lake, Databricks                                                                                     |
| **Languages**          | Python, PySpark                                                                                                 |
| **Modeling Libraries** | `scikit-learn`, `scikit-uplift` (`sklift`)                                                                      |
| **Visualization**      | `matplotlib`, `seaborn`                                                                                         |
| **Dataset**            | [Criteo Uplift Modeling Dataset (1M rows)


## 🗂️ Repository Structure

```
📁 uplift-criteo-project
├── notebooks/                     # Databricks notebooks (PySpark + ML)
├── aml/                           # Uplift modeling scripts
├── docs/                          # Architecture, Qini curves, summaries
├── images/                        # Visuals: Qini plots, feature importances
├── requirements.txt               # Python package dependencies
└── README.md                      # Project overview
```

---

## 🔍 Methodology

We implemented and compared two modeling frameworks:

| Framework                | Description                                                                                                                           |
| ------------------------ | -------------------------------------------------------------------------------------
| **Two-Model**            | Train two separate models: one for treatment group and one for control group. The difference in predicted probabilities gives uplift. |
| **Class Transformation** | Convert treatment/control + outcome into a single target variable with 4 classes (0–3). Trained using single multiclass classifier.   |

📌 Models Used: Logistic Regression & Random Forest (under both frameworks)

---

## 📊 Visualizations

| 📈 Plot                      
| -----------------------------
| Qini Curves (All Models)     
| Feature Importance (Optional) 
| Architecture Diagram         

---

## 📈 Model Evaluation

✔ Evaluation Metric: **Qini Curve** (measures incremental uplift gain)

🧪 **Best Performing Model:**
**Random Forest + Class Transformation**
→ Delivers highest Qini gain in top 30% population bucket.

---

## 💼 Business Insights

* 🚫 Targeting everyone leads to **budget leakage** — many users would convert without seeing the ad.
* ✅ Focus on **top uplift deciles** improves conversion uplift by **2.1×**.
* 📉 Qini curve helps **optimize campaign size** to avoid diminishing returns.


---

## 🔁 Reproducibility

* Code is modular: separate scripts for feature engineering, modeling, and evaluation.
* Compatible with Databricks notebooks.
* Environment: Python 3.9, `sklearn`, `sklift`, `matplotlib`, `seaborn`.


---

## 🧠 Key Learnings

* Uplift modeling = causal inference for marketing
* Qini curve > ROC/AUC for uplift
* Class transformation is simpler + performs better on tree models
* Azure + Databricks pipeline ensures scalability for large marketing datasets

Let’s lock in the final steps!
```
