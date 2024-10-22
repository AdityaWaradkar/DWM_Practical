# Experiment 5: Implementation of Data Discretization & Visualization

## Objective:
To implement a data discretization method and visualize the discretized data using a suitable visualization technique.

---

## Theory:

### What is Data Discretization?
Data discretization is the process of converting continuous data into discrete buckets or intervals. It helps simplify the analysis of data by reducing the number of possible values and grouping similar values together. It is commonly used in machine learning preprocessing and data mining.

#### Types of Data Discretization:
1. **Binning (Equal Width / Equal Frequency)**: 
   - **Equal Width Binning**: Divides the range of the data into intervals of equal size.
   - **Equal Frequency Binning**: Divides the data into intervals that each contain the same number of data points.
2. **Clustering-Based Discretization**: Grouping data points into clusters, then assigning cluster labels as discrete values.
3. **Decision Tree-Based Discretization**: Using a decision tree to generate cut points based on the splits of continuous attributes.

---

## Steps for Data Discretization:
1. Choose a discretization method (e.g., equal-width binning).
2. Determine the number of bins or intervals.
3. Apply the discretization method to the data.
4. Assign each data point to its corresponding bin.

---

## Algorithm: Equal Width Binning

1. Divide the range of data into `k` equal-width intervals (bins).
2. Determine the width of each bin as:  
   \[
   \text{bin width} = \frac{\text{max value} - \text{min value}}{k}
   \]
3. Assign each data point to the corresponding bin based on its value.

---

## Implementation:

### Libraries Required:
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
