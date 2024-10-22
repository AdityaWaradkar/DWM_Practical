# Experiment 6: Demonstrate Classification, Clustering, and Association Algorithms using WEKA

## Objective
To demonstrate how to implement classification, clustering, and association algorithms using the WEKA data mining tool.

## Datasets
1. **Iris Dataset**: A classic dataset containing samples of iris flowers with features such as sepal length, sepal width, petal length, petal width, and species.
2. **Groceries Dataset**: A dataset containing transactions from a grocery store for association rule mining.

## Step 1: Install WEKA
Download and install WEKA from the official website: [WEKA Download](https://www.cs.waikato.ac.nz/ml/weka/downloading.html).

## Step 2: Open WEKA
1. Launch the WEKA application.
2. Choose to use the **Explorer** mode.

## Step 3: Classification with WEKA
1. **Load the Iris Dataset**:
   - Open the `iris.arff` file.

2. **Choose a Classifier**:
   - Select the `J48` classifier.

3. **Set the Test Options**:
   - Use "Cross-validation" with 10 folds.

4. **Run the Classifier**:
   - Click "Start" and review the results.

## Step 4: Clustering with WEKA
1. **Load the Iris Dataset** (if not already loaded).

2. **Choose a Clustering Algorithm**:
   - Select the `KMeans` algorithm.

3. **Set the Number of Clusters**:
   - Set to 3 for the Iris dataset.

4. **Run the Clustering Algorithm**:
   - Click "Start" and visualize the results.

## Step 5: Association Rule Mining with WEKA
1. **Load the Groceries Dataset**:
   - Open the `groceries.arff` file.

2. **Choose an Association Algorithm**:
   - Select `Apriori`.

3. **Set the Parameters**:
   - Minimum support = 0.01, confidence = 0.5.

4. **Run the Association Algorithm**:
   - Click "Start" and review the generated association rules.

## Conclusion
This experiment demonstrated how to apply classification, clustering, and association algorithms using WEKA on the Iris and Groceries datasets, providing insights into data mining techniques.
