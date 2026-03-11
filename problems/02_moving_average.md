# Moving Average — Smoothing Heart Rate Data

## 1. Introduction

Wearable health devices collect data continuously.  
However, sensor readings are rarely perfectly stable.

Small fluctuations often appear due to:

- body movement  
- sensor noise  
- device precision limits  

Because of this, raw measurements can be **noisy**.  
A common technique used in data analysis and machine learning pipelines is **smoothing**.

One simple and powerful smoothing technique is the **moving average**.

---

## 2. The Problem

Imagine you are working on a **patient monitoring system**.

A wearable device records **heart rate every minute**.

Example readings:

```python
[72, 75, 78, 76, 80, 82, 79]
```
These readings fluctuate slightly.

To reduce noise, you decide to calculate a moving average with a window size of 3.

This means each new value is calculated as the average of three consecutive readings.

Example calculations:
```python
(72 + 75 + 78) / 3
(75 + 78 + 76) / 3
(78 + 76 + 80) / 3
(76 + 80 + 82) / 3
(80 + 82 + 79) / 3
```
The result will be a smoothed version of the original signal.

Your task:  Write a Python function that calculates the moving average for a list of heart rate readings.
