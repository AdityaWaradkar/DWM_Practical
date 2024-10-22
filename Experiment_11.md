# Experiment 11: Implementation of KNN Algorithm

## Goal:
To implement the **K-Nearest Neighbors (KNN)** algorithm and understand how to classify data points based on their nearest neighbors in the feature space.

---

## What is KNN?
KNN is a **supervised learning** algorithm used for classification and regression. It classifies a data point based on how its neighbors are classified. The algorithm assumes that similar instances are found in close proximity.

### Key Concepts:
1. **K**: The number of nearest neighbors to consider when making a classification.
2. **Distance Metric**: A method for measuring the distance between data points (e.g., Euclidean distance).
3. **Majority Vote**: The class that appears most frequently among the K nearest neighbors is assigned to the data point.

---

## Steps of the KNN Algorithm:

### 1. **Choose the number of neighbors (K)**:
   Decide how many nearest neighbors to consider for making a prediction.

### 2. **Calculate Distance**:
   Compute the distance between the data point to be classified and all other data points in the dataset.

### 3. **Find Nearest Neighbors**:
   Identify the K nearest neighbors based on the calculated distances.

### 4. **Majority Voting**:
   For classification, determine the class that has the majority among the K neighbors and assign it to the data point.

### 5. **Return Prediction**:
   Return the predicted class or value for the data point.

---

## Example of KNN:

### Sample Data Points:
Consider the following 2D data points, where class 0 is represented by red and class 1 by blue:
- Point A(1, 2): Class 0 (red)
- Point B(1, 4): Class 0 (red)
- Point C(1, 0): Class 1 (blue)
- Point D(4, 2): Class 1 (blue)
- Point E(4, 4): Class 1 (blue)
- Point F(4, 0): Class 1 (blue)

### Step 1: Choose K
Let’s say we choose K=3.

### Step 2: Calculate Distance
Calculate the distance from a new point, G(3, 3), to all other points.

### Step 3: Find Nearest Neighbors
Identify the three nearest points to G:
- Nearest points: D(4, 2), E(4, 4), B(1, 4)

### Step 4: Majority Voting
Count the classes of the nearest points:
- Class 0 (red): 1 (B)
- Class 1 (blue): 2 (D, E)

### Step 5: Return Prediction
The predicted class for point G(3, 3) is Class 1 (blue).

---

## Python Implementation:

### Step 1: Import Necessary Libraries
```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.datasets import make_classification
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier
