# Experiment 7: Implementation of Clustering Algorithm (K-means)

## Goal:
To implement the **K-means Clustering** algorithm and understand how to group similar data points into clusters based on their features.

---

## What is K-means Clustering?
K-means Clustering is an unsupervised learning algorithm used to partition a dataset into **K distinct clusters**. Each cluster is represented by its centroid (mean of all points in the cluster).

### Key Concepts:
1. **Centroid**: The center point of a cluster, calculated as the mean of all points in that cluster.
2. **Cluster**: A group of data points that are similar to each other based on a distance metric (typically Euclidean distance).
3. **Iterations**: The process of updating centroids and reassigning points to clusters until convergence.

---

## Steps of the K-means Algorithm:

### 1. **Initialize Centroids:**
   Randomly select K data points from the dataset as initial centroids.

### 2. **Assign Clusters:**
   For each data point, calculate the distance to each centroid and assign the point to the nearest centroid.

### 3. **Update Centroids:**
   After assigning all points to clusters, calculate the new centroids as the mean of the points in each cluster.

### 4. **Repeat:**
   Repeat steps 2 and 3 until the centroids no longer change significantly or until a specified number of iterations is reached.

---

## Example of K-means Clustering:

### Sample Data Points:
Consider the following 2D data points:
- A(1, 2)
- B(1, 4)
- C(1, 0)
- D(4, 2)
- E(4, 4)
- F(4, 0)

### Step 1: Initialize Centroids
Let’s say we choose K=2 and randomly select D(4, 2) and A(1, 2) as initial centroids:
- Centroid1: (4, 2)
- Centroid2: (1, 2)

### Step 2: Assign Clusters
Calculate distances and assign points:
- A to Centroid2 (1,2) → Cluster 1
- B to Centroid2 (1,2) → Cluster 1
- C to Centroid2 (1,2) → Cluster 1
- D to Centroid1 (4,2) → Cluster 2
- E to Centroid1 (4,2) → Cluster 2
- F to Centroid1 (4,2) → Cluster 2

### Step 3: Update Centroids
Calculate new centroids:
- New Centroid1 = mean of Cluster 1 points = (1, 2)
- New Centroid2 = mean of Cluster 2 points = (4, 2)

### Step 4: Repeat
Continue the assignment and updating steps until convergence.

---

## Python Implementation:

### Step 1: Import Necessary Libraries
```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.datasets import make_blobs
from sklearn.cluster import KMeans
