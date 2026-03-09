# The Normalizer — Preparing Health Data for Machine Learning

## 1. Introduction

In many AI and machine learning systems, raw data cannot be used directly.

Data often comes from different sources and can exist on completely different scales.  
Before feeding this data into a machine learning model, it usually needs to be **normalized**.

Normalization transforms data so that all values fall within a **common range**, typically:

```python
[0, 1]
```
This makes training more stable and helps models learn patterns more effectively.

In this exercise, we will simulate a **real-world health scenario** involving wearable devices that track heart rate.

---

## 2. The Problem

Imagine you are building a small system that analyzes **heart rate data from wearable health devices**.

You receive raw heart rate readings like this:

```python
[72, 80, 88, 96]
```

These numbers represent heartbeats per minute (BPM) recorded at different times.

Now here is the challenge.

Machine learning models usually perform better when the input data is scaled to a common range.

A very common technique is to convert values into the range:
```python
[0, 1]
```
So the data:
```python
[72, 80, 88, 96]
```
should become something like:
```python
[0.0, 0.33, 0.66, 1.0]

```
Your task is simple.

You need to write a Python function that normalizes these health measurements.

Before writing any code, pause for a moment and think about the transformation.

What information from the list do you need?

How do you convert the smallest value to 0?

How do you convert the largest value to 1?

Hint: The solution depends on understanding the minimum and maximum values in the dataset.
