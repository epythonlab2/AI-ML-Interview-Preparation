# Transaction Outlier Detection

## Problem

In many financial systems, machine learning models are trained on historical transaction data.  
However, real-world financial data often contains unusual values that can distort model training.

For example, most daily transactions for a user might fall within a typical range, but occasionally a transaction appears that is far outside this pattern. This could happen due to:

- fraud attempts  
- data entry errors  
- system glitches  

Example transaction data:
```python
[52, 48, 50, 55, 53, 49, 51, 500]
```

The value **500** is significantly larger than the rest of the transactions and may represent an abnormal or suspicious transaction.

Before using this data to train a machine learning model, it is important to detect such anomalies.

## Your Task

Write a function that identifies outliers in a list of transaction amounts using the **Z-score method**.

The function should:

- Accept a list of numerical transaction values.
- Calculate the **mean** of the transactions.
- Calculate the **standard deviation**.
- Compute the **Z-score** for each transaction.
- Return all transactions whose **absolute Z-score is greater than a threshold**.

Default threshold:
```python
2
```

Transactions exceeding this threshold should be considered **outliers**.
