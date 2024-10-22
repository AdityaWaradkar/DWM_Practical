# Experiment 4: Implementation of Bayesian Algorithm

## Goal:
To use the Naive Bayes method to classify data into different groups using Python.

---

## What is Naive Bayes?
Naive Bayes is a way of guessing which group something belongs to by looking at its features. It uses a formula called **Bayes' Theorem** to figure this out.

### Bayes' Theorem (in simple words):
This theorem helps us find the probability (or chance) of something happening based on previous knowledge. For example, if we know the chance of rain on certain days, we can guess the chance of rain today based on today's weather conditions.

The formula is:
\[
P(\text{Class}|\text{Feature}) = \frac{P(\text{Feature}|\text{Class}) \cdot P(\text{Class})}{P(\text{Feature})}
\]

- **P(Class|Feature)**: The chance of being in a group given the feature.
- **P(Feature|Class)**: The chance of having a feature in a specific group.
- **P(Class)**: The overall chance of being in a group.
- **P(Feature)**: The overall chance of having a feature.

### Types of Naive Bayes:
1. **Gaussian Naive Bayes**: For continuous data (like temperature).
2. **Multinomial Naive Bayes**: For counting data (like word counts).
3. **Bernoulli Naive Bayes**: For yes/no (binary) data.

---

## How Naive Bayes Works (Step-by-Step):
1. Look at all the features (data points).
2. Calculate how likely each feature is in each group.
3. Use the formula to guess which group something belongs to.
4. Choose the group with the highest chance.

---

## Implementation in Python:

### Step 1: Load Libraries
```python
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.naive_bayes import GaussianNB
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report
