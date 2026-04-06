# Interview Challenge: Machine Learning Engineering

## Problem 4: Detecting Data Leakage in a Dataset

### The Scenario
You are developing a predictive model to identify customer churn. During the initial training phase, your model achieves near-perfect accuracy—an "ideal" result that immediately raises a red flag for experienced engineers.

The likely culprit is **Data Leakage**. This occurs when your training features contain information that would not be available at the time of prediction in a real-world setting. In this case, a feature might be a direct proxy for the target variable, essentially "giving the model the answer" and leading to an over-optimistic but useless model.

---

### The Task
Your goal is to write a pre-processing function that audits a dataset for potential leakage before it reaches the training pipeline.

**Requirements:**
1.  **Input:** The function should accept a dataset (list of dictionaries) and the name of the `target_column`.
2.  **Logic:** Identify features that have an unnaturally high correlation or a 1:1 match with the target variable.
3.  **Output:** Return a list of strings representing the names of the "leaked" features that should be dropped.

---

### Example Dataset

| age | monthly_spend | **churn** (Target) | account_closed (Feature) |
| :--- | :--- | :--- | :--- |
| 25 | 200 | **0** | 0 |
| 40 | 500 | **1** | 1 |
| 30 | 300 | **0** | 0 |

> **Audit Observation:** In the sample above, `account_closed` perfectly mirrors the `churn` status. Since an account is only closed *after* a customer has churned, this feature is a leaky variable and must be removed.

---

### Implementation Brief
Write a function `identify_leakage(data, target_column)` to detect these dependencies. 

**Pro-Tip:** While a perfect 1.0 correlation is easy to spot, think about how you might handle "near-perfect" correlations (e.g., 0.99) that often occur in larger, messier production datasets.
