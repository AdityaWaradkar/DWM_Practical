# Experiment 8: Implementation of Agglomerative Clustering

## Goal:
To implement the **Agglomerative Clustering** algorithm, a type of hierarchical clustering, and understand how to group similar data points based on distance metrics.

---

## What is Agglomerative Clustering?
Agglomerative Clustering is a **bottom-up** approach to clustering. It starts with each data point as its own cluster and iteratively merges the closest pairs of clusters until a stopping criterion is met (e.g., a specified number of clusters or a threshold distance).

### Key Concepts:
1. **Cluster**: A collection of data points that are similar to each other.
2. **Distance Metric**: A method for measuring the distance between data points (e.g., Euclidean distance).
3. **Dendrogram**: A tree-like diagram that illustrates the arrangement of clusters.

---

## Steps of the Agglomerative Clustering Algorithm:

### 1. **Initialize Clusters:**
   Start with each data point as its own cluster.

### 2. **Calculate Distance:**
   Compute the distance between each pair of clusters.

### 3. **Merge Closest Clusters:**
   Identify the two closest clusters and merge them into a single cluster.

### 4. **Update Distance:**
   Recalculate the distances between the new cluster and all other clusters.

### 5. **Repeat:**
   Repeat steps 3 and 4 until a specified number of clusters is formed or all points are merged into one cluster.

---

## Example of Agglomerative Clustering:

### Sample Data Points:
Consider the following 2D data points:
- A(1, 2)
- B(1, 4)
- C(1, 0)
- D(4, 2)
- E(4, 4)
- F(4, 0)

### Step 1: Initialize Clusters
Each point is its own cluster:
- Clusters: {A}, {B}, {C}, {D}, {E}, {F}

### Step 2: Calculate Distance
Calculate the pairwise distances (using Euclidean distance):
- Distance(A, B) = √((1-1)² + (2-4)²) = 2
- Distance(A, C) = √((1-1)² + (2-0)²) = 2
- Distance(A, D) = √((1-4)² + (2-2)²) = 3
- Distance(A, E) = √((1-4)² + (2-4)²) = 3.605
- Distance(A, F) = √((1-4)² + (2-0)²) = 3.605
- (Continue for all pairs...)

### Step 3: Merge Closest Clusters
- Merge A and C: New Cluster {A, C}

### Step 4: Update Distance
- Recalculate distances:
- Distance({A, C}, B) = 2
- (Continue for other distances...)

### Step 5: Repeat
Continue merging until a stopping criterion is met.

---

## Python Implementation:

### Step 1: Import Necessary Libraries
```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.cluster.hierarchy import dendrogram, linkage
from sklearn.datasets import make_blobs
