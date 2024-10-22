# Experiment 10: Implementation of PageRank Algorithm

## Goal:
To implement the **PageRank algorithm** using Python and to calculate the rank (importance) of each page in a network of web pages.

---

## What is PageRank?
PageRank is an algorithm used to rank web pages based on their importance. The importance of a page depends on the number and quality of links it receives from other pages. 

### How Does PageRank Work?
- Every page starts with the same rank (or importance score).
- Pages that are linked by other important pages gain a higher rank.
- This process repeats until the rank values stabilize.

### Key Concepts:
1. **Links (edges)**: The connections from one page to another.
2. **PageRank value**: A score that represents the importance of a page. 
3. **Damping Factor**: A probability (usually set to 0.85) that a user continues clicking on links.

---

## PageRank Algorithm

The PageRank algorithm can be broken down into these steps:

### 1. **Initial Setup:**
- Let **n** be the total number of web pages.
- Set an initial PageRank value for each page. Initially, each page is assigned the same rank: 
  $$ 
  \text{Initial Rank} = \frac{1}{n} 
  $$
  
### 2. **Link Matrix:**
- Create a matrix that represents links between pages. In this matrix:
  - A `1` indicates a link from one page to another.
  - A `0` indicates no link between two pages.

### 3. **Calculate PageRank Iteratively:**
- For each page, update its rank based on the ranks of the pages linking to it. 
- The updated rank is calculated as:
  $$
  PR(p_i) = \frac{1 - d}{n} + d \times \sum_{p_j \in \text{in-links to } p_i} \frac{PR(p_j)}{\text{out-links from } p_j}
  $$
  
  Where:
  - \(PR(p_i)\): The PageRank of page \(i\).
  - \(PR(p_j)\): The PageRank of page \(j\) linking to \(i\).
  - \(d\): Damping factor (usually set to 0.85).
  - \(n\): Total number of pages.
  - Out-links from \(p_j\): Number of outgoing links from page \(j\).

### 4. **Repeat Until Convergence:**
- Repeat the process for all pages and update their ranks.
- Stop when the ranks stabilize (i.e., the difference between the old and new rank is very small for all pages).

---

## Example of PageRank Calculation:

Let's say we have 4 pages and the following links between them:

- Page A links to Page B and C.
- Page B links to Page A and C.
- Page C links to Page A.
- Page D links to Page C.

We represent this as a **link matrix**:

| Pages | A  | B  | C  | D  |
|-------|----|----|----|----|
| **A** | 0  | 1  | 1  | 0  |
| **B** | 1  | 0  | 1  | 0  |
| **C** | 1  | 0  | 0  | 0  |
| **D** | 0  | 0  | 1  | 0  |

- **Step 1**: Initialize the ranks for each page. Since there are 4 pages, the initial rank is:
  $$
  PR(A) = PR(B) = PR(C) = PR(D) = \frac{1}{4} = 0.25
  $$

- **Step 2**: Use the formula to update the PageRank for each page, considering the damping factor (e.g., 0.85).

  Example update for **Page A**:
  $$
  PR(A) = \frac{1 - 0.85}{4} + 0.85 \times \left( \frac{PR(C)}{1} \right)
  $$
  
  Repeat this process for all pages.

---

## Python Implementation:

### Step 1: Import Necessary Libraries
```python
import numpy as np
