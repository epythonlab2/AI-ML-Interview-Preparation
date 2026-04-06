# Interview Challenge: Machine Learning Engineering

## Problem 5: Detecting Data Drift in Production

### The Scenario
You have successfully deployed a machine learning model that performed exceptionally well during the offline training phase. However, after a few weeks in production, you notice a significant decline in the model's predictive accuracy. 

The culprit is likely **Data Drift**: a phenomenon where the statistical properties of the input data change over time, rendering the patterns learned during training obsolete. To maintain model reliability, you need to implement a monitoring system that flags when the incoming production data deviates significantly from the baseline training distribution.

---

### The Task
Your objective is to build a diagnostic function that quantifies the shift between two datasets. 

**Requirements:**
1.  **Input:** The function should accept two numerical arrays: `train_data` (the baseline) and `new_data` (the production stream).
2.  **Metric:** Calculate the absolute difference between the **means** of the two datasets.
3.  **Logic:** Compare this difference against a predefined `threshold`. 
4.  **Output:** Return a boolean value (`True` if drift is detected, `False` otherwise) and the calculated drift magnitude.

---

### Example Data

| Dataset | Sample Observations |
| :--- | :--- |
| **Training Data** | `[10, 12, 11, 13, 12, 11, 10]` |
| **New Data** | `[20, 22, 21, 23, 22, 24, 21]` |

> **Note:** In the example above, the mean has clearly shifted from roughly **11.3** to **21.8**. With a threshold of **5.0**, your function should successfully flag this as a drift event.

---

### Implementation Brief
Write a function `detect_drift(train_data, new_data, threshold)` to automate this check. Consider how you might handle edge cases, such as empty lists or extreme outliers, to make the function production-ready.
