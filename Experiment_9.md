# Experiment 9: Implementation of Association Rule Mining Algorithm (Apriori)

## Goal:
To implement the **Apriori algorithm** for finding association rules in a dataset and understanding how to derive rules based on itemset frequencies.

---

## What is the Apriori Algorithm?
The Apriori algorithm is a classic algorithm used in data mining for discovering frequent itemsets in transactional databases and generating association rules. 

### Key Concepts:
1. **Itemset**: A collection of one or more items.
2. **Support**: The support of an itemset is the proportion of transactions in the database that contain that itemset.
   - **Formula**: 
   $$
   \text{Support}(X) = \frac{\text{Number of transactions containing } X}{\text{Total number of transactions}}
   $$
3. **Confidence**: The confidence of a rule \( A \rightarrow B \) is the proportion of transactions that contain \( A \) which also contain \( B \).
   - **Formula**: 
   $$
   \text{Confidence}(A \rightarrow B) = \frac{\text{Support}(A \cup B)}{\text{Support}(A)}
   $$
4. **Lift**: The lift of a rule is the ratio of the observed support to that expected if \( A \) and \( B \) were independent.
   - **Formula**: 
   $$
   \text{Lift}(A \rightarrow B) = \frac{\text{Support}(A \cup B)}{\text{Support}(A) \times \text{Support}(B)}
   $$

---

## Steps of the Apriori Algorithm:

### 1. **Generate Frequent Itemsets:**
   - Start with individual items and count their occurrences (1-itemsets).
   - Generate candidate itemsets from the frequent itemsets of the previous step.
   - Calculate support for these candidate itemsets.
   - Keep only the itemsets that meet a minimum support threshold.

### 2. **Generate Association Rules:**
   - From the frequent itemsets, generate rules and calculate their confidence and lift.
   - Keep only those rules that meet the minimum confidence threshold.

---

## Example of Apriori Algorithm Calculation:

### Sample Transactions:
| Transaction ID | Items                     |
|----------------|---------------------------|
| 1              | {Milk, Bread, Diaper}     |
| 2              | {Milk, Bread}             |
| 3              | {Milk, Diaper}            |
| 4              | {Bread, Diaper}           |
| 5              | {Milk, Bread, Diaper}     |

### Step 1: Count Support for 1-itemsets:
- **Milk**: 4/5 = 0.8
- **Bread**: 4/5 = 0.8
- **Diaper**: 3/5 = 0.6

### Step 2: Generate Frequent Itemsets (Minimum Support = 0.6):
- **Frequent 1-itemsets**: {Milk}, {Bread}, {Diaper}

### Step 3: Count Support for 2-itemsets:
- **{Milk, Bread}**: 3/5 = 0.6
- **{Milk, Diaper}**: 2/5 = 0.4
- **{Bread, Diaper}**: 2/5 = 0.4

### Step 4: Generate Frequent 2-itemsets (Minimum Support = 0.6):
- **Frequent 2-itemsets**: {Milk, Bread}

### Step 5: Generate Association Rules:
From **{Milk, Bread}**:
- **Rule**: Milk → Bread
  - **Support**: 3/5 = 0.6
  - **Confidence**: \( \frac{Support(Milk, Bread)}{Support(Milk)} = \frac{3/5}{4/5} = 0.75 \)
  - **Lift**: \( \frac{Support(Milk, Bread)}{Support(Milk) \times Support(Bread)} = \frac{3/5}{(4/5) \times (4/5)} = \frac{0.6}{0.64} \approx 0.9375 \)

---

## Python Implementation:

### Step 1: Import Necessary Libraries
```python
from itertools import combinations
from collections import defaultdict
