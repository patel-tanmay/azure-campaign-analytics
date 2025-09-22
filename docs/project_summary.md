# Project Summary – Uplift Modeling with Criteo Dataset


**Business Objective:**
Optimize marketing spend by identifying which users are most likely to respond positively to targeted campaigns (i.e., conversions) using Uplift Modeling.


**Approach:**
- Leverage the Criteo Uplift Modeling Dataset
- Use Two-Model and Class Transformation strategies
- Model using Logistic Regression and Random Forest
- Evaluate performance using Qini Curve


**Key Insights:**
- Class Transformation with Logistic Regression showed best uplift in top decile
- Qini analysis shows targeting top 30% yields significant incremental conversions


**Tools Used:**
- Azure Data Lake + Azure Databricks (PySpark + scikit-uplift)
- Python (pandas, matplotlib, scikit-learn, sklift)
