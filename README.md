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
