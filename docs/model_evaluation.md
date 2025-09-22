# Model Evaluation Summary


| Model               | Uplift Strategy         | Performance Summary |
|---------------------|-------------------------|-----------------------------------|
| Logistic Regression | Two-Model               | Decent uplift, underperforms at tail |
| Logistic Regression | Class Transformation    | Best overall uplift, smooth Qini curve |
| Random Forest       | Two-Model               | Slight overfitting, unstable Qini |
| Random Forest       | Class Transformation    | Good initial gain, but plateaus early |


**Conclusion:** Use Class Transformation with Logistic Regression for production.
