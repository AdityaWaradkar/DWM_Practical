# Viva Questions and Answers for Data Warehousing and Data Mining Experiments

## Experiment 1: One Case Study on Building Data Warehouse/Data Mart

1. **What is a data warehouse and how does it differ from a data mart?**
   - A **data warehouse** is a large storage system that holds data from different sources for analysis. A **data mart** is a smaller version that focuses on a specific subject or department.

2. **Can you explain the purpose of dimensional modeling in a data warehouse?**
   - Dimensional modeling helps organize data in a way that makes it easy to retrieve and analyze. It structures the data into dimensions (like time or product) and facts (like sales).

3. **What are the key components of a star schema?**
   - A star schema has a central **fact table** that contains quantitative data (like sales), surrounded by **dimension tables** that provide context (like time, location, or product).

4. **How does a snowflake schema differ from a star schema?**
   - In a snowflake schema, dimension tables are normalized, meaning they are split into multiple related tables. This can save space but makes the model more complex.

5. **Describe the process of designing a dimensional model.**
   - The process involves identifying key business questions, determining what data is needed, creating dimension and fact tables, and defining relationships between them.

6. **What factors should be considered when defining the problem statement for the case study?**
   - Consider the goals of the data warehouse, the data sources, user needs, and how the data will be used for analysis.

## Experiment 2: Implementation of All Dimension Tables and Fact Tables

1. **What are dimension tables and fact tables in a data warehouse?**
   - **Dimension tables** hold descriptive data (like product names), while **fact tables** hold numerical data (like sales amounts).

2. **How do you determine which attributes should be included in a dimension table?**
   - Choose attributes that provide meaningful context for analysis, such as names, categories, and dates that help describe the facts.

3. **Explain the role of primary keys and foreign keys in fact and dimension tables.**
   - A **primary key** uniquely identifies a record in a table. A **foreign key** links a record in one table to a record in another, creating relationships between tables.

4. **What is the significance of grain in a fact table?**
   - The **grain** defines the level of detail in the fact table. For example, if the grain is daily sales, each record represents sales for one day.

5. **How do you ensure data integrity during the implementation of these tables?**
   - Use constraints, like primary keys, and validation rules to make sure the data is accurate and consistent across tables.

## Experiment 3: Implementation of OLAP Operations

1. **What is OLAP and how is it different from OLTP?**
   - **OLAP** (Online Analytical Processing) is for analyzing data and generating reports. **OLTP** (Online Transaction Processing) is for managing daily transactions, like sales.

2. **Can you define and explain the following OLAP operations: Slice, Dice, Rollup, Drilldown, and Pivot?**
   - **Slice**: Select a single dimension to view a specific slice of data.
   - **Dice**: Select multiple dimensions to create a smaller cube of data.
   - **Rollup**: Aggregate data to a higher level (like summarizing daily sales to monthly).
   - **Drilldown**: Break data down to a lower level of detail (like viewing sales by day instead of by month).
   - **Pivot**: Rotate the data to view it from different perspectives (like swapping rows and columns).

3. **Provide an example of how you would perform a rollup operation.**
   - If you have daily sales data, a rollup could combine it to show total sales for each month instead.

4. **How does the slice operation differ from the dice operation?**
   - **Slice** focuses on one dimension, while **dice** looks at multiple dimensions simultaneously to create a sub-cube of data.

5. **Why are OLAP operations important in data analysis?**
   - OLAP operations allow users to explore and analyze large amounts of data quickly, helping them make informed decisions.

## Experiment 4: Implementation of Bayesian Algorithm

1. **What is the Bayesian algorithm and what type of problems does it solve?**
   - The Bayesian algorithm is a statistical method used for classification tasks, like spam detection or diagnosis in medicine. It uses prior knowledge and updates beliefs based on new evidence.

2. **Explain Bayes' theorem in simple terms.**
   - Bayes' theorem shows how to update the probability of a hypothesis based on new evidence. It combines prior probability with likelihood to give a new probability.

3. **How do you apply the Bayesian algorithm for classification tasks?**
   - You calculate the probability of each class based on the features of the data and then choose the class with the highest probability.

4. **What is prior probability and how does it affect the outcome?**
   - **Prior probability** is the initial belief about the probability of a class before seeing new data. It influences the final classification by weighing the initial assumption.

5. **Discuss the advantages and limitations of using the Bayesian algorithm.**
   - **Advantages**: Simple, interpretable, and works well with small datasets.
   - **Limitations**: Assumes independence between features, which may not always hold true.

## Experiment 5: Implementation of Data Discretization & Visualization

1. **What is data discretization, and why is it used in data mining?**
   - Data discretization is the process of converting continuous data into discrete categories. It simplifies analysis and makes it easier to interpret results.

2. **Describe the different methods of data discretization.**
   - Common methods include:
     - **Equal-width**: Divides data into equal ranges.
     - **Equal-frequency**: Divides data so each category has the same number of records.
     - **Clustering-based**: Groups similar data points into categories.

3. **How do you visualize discrete data effectively?**
   - Use charts like bar graphs, pie charts, or histograms to show the frequency of each category clearly.

4. **What tools or libraries can you use for data visualization?**
   - Common tools include **Matplotlib**, **Seaborn**, and **Tableau** for creating visualizations.

5. **Explain the importance of data visualization in data analysis.**
   - Data visualization helps to quickly understand trends, patterns, and outliers in data, making it easier to communicate findings.

## Experiment 6: Classification, Clustering, Association Algorithm Demonstration

1. **What is the difference between classification and clustering?**
   - **Classification** assigns predefined labels to data based on features. **Clustering** groups similar data points without predefined labels.

2. **Can you explain how the WEKA/R tool is used for data mining tasks?**
   - WEKA and R are software tools that provide algorithms for data mining tasks like classification, clustering, and association. They offer user-friendly interfaces and coding environments.

3. **Describe an example of a classification algorithm you have used.**
   - An example is the **Decision Tree** algorithm, which splits data into branches based on feature values to classify the data points.

4. **How do association algorithms work? Can you give an example?**
   - Association algorithms find relationships between variables in a dataset. An example is market basket analysis, where it identifies products often bought together.

5. **What are the challenges in implementing clustering algorithms?**
   - Challenges include choosing the right number of clusters, dealing with noise and outliers, and ensuring the algorithm scales well with large datasets.

## Experiment 7: Implementation of Clustering Algorithm (K-means/K-medoids)

1. **What is the K-means algorithm and how does it work?**
   - K-means is a clustering algorithm that groups data into K clusters by assigning each data point to the nearest cluster center and then updating the centers based on the assignments.

2. **How do you choose the number of clusters (K) in K-means?**
   - You can use methods like the **elbow method**, where you plot the total variance explained against K and look for a point where the decrease in variance slows down.

3. **What are the advantages and disadvantages of K-means clustering?**
   - **Advantages**: Simple to implement and works well with large datasets.
   - **Disadvantages**: Sensitive to outliers and requires you to specify K in advance.

4. **Explain the difference between K-means and K-medoids clustering.**
   - K-medoids uses actual data points as centers (medoids) instead of the mean of points, making it more robust to outliers.

5. **What distance metrics can be used in K-means clustering?**
   - The most common metric is **Euclidean distance**, but others like **Manhattan distance** can also be used depending on the data.

## Experiment 8: Implementation of Hierarchical Clustering (Agglomerative Clustering)

1. **What is hierarchical clustering and how does it differ from K-means?**
   - Hierarchical clustering creates a tree of clusters and does not require specifying the number of clusters in advance. K-means requires this number beforehand.

2. **Can you explain the agglomerative clustering approach?**
   - Agglomerative clustering starts with each data point as its own cluster and then repeatedly merges the closest clusters until all points are in one cluster or a stopping criterion is met.

3. **What is a dendrogram, and how is it useful in hierarchical clustering?**
   - A **dendrogram** is a tree diagram that shows the arrangement of clusters. It helps visualize the relationships between clusters and decide on the number of clusters.

4. **What are the advantages and limitations of agglomerative clustering?**
   - **Advantages**: Does not require a pre-defined number of clusters and can capture complex cluster shapes.
   - **Limitations**: Can be computationally expensive with large datasets and sensitive to noise.

5. **How do you decide the number of clusters in hierarchical clustering?**
   - You can cut the dendrogram at a specific height to determine the desired number of clusters based on how you want to group the data.

## Experiment 9: Implementation of Association Rule Mining Algorithm (Apriori)

1. **What is association rule mining, and where is it typically used?**
   - Association rule mining finds interesting relationships or patterns between variables in large datasets. It's often used in market basket analysis.

2. **Explain the Apriori algorithm and its main steps.**
   - The Apriori algorithm works by:
     - Finding frequent itemsets (combinations of items that appear together).
     - Generating association rules from these itemsets.

3. **What are support, confidence, and lift in the context of association rules?**
   - **Support** measures how often an itemset appears in the dataset. 
   - **Confidence** indicates how often a rule is true (e.g., if A is bought, how often is B also bought).
   - **Lift** compares the likelihood of a rule to what would be expected if the items were independent.

4. **How do you handle large datasets when using the Apriori algorithm?**
   - Use techniques like sampling, data pruning, or more efficient data structures to reduce the amount of data processed at once.

5. **Can you provide an example of a real-world application of association rule mining?**
   - A common application is in retail, where it helps identify products frequently purchased together, allowing stores to optimize product placement and promotions.

## Experiment 10: Implementation of Page Rank/HITS Algorithm

1. **What is the purpose of the PageRank algorithm?**
   - PageRank ranks web pages based on their importance, helping search engines decide which pages to show in search results.

2. **How does the PageRank algorithm determine the importance of web pages?**
   - It looks at the number and quality of links to a page. More high-quality links increase a page's importance.

3. **Explain the concept of link analysis in the context of PageRank.**
   - Link analysis examines how web pages are linked to each other. Pages with more incoming links from other important pages rank higher.

4. **What are the differences between the PageRank algorithm and the HITS algorithm?**
   - PageRank focuses on overall importance through link structure, while HITS identifies two types of pages: hubs (linking to many others) and authorities (being linked to by many).

5. **How can PageRank be applied in search engine optimization?**
   - Improving the quality and quantity of inbound links can enhance a page's PageRank, making it more likely to appear higher in search results.

## Experiment 11: Implementation of KNN Algorithm

1. **What is the K-Nearest Neighbors (KNN) algorithm, and how does it work?**
   - KNN is a simple classification algorithm that assigns a label to a data point based on the majority label of its K nearest neighbors.

2. **How do you choose the value of K in KNN?**
   - You can choose K based on cross-validation or by experimenting with different values to see which gives the best results.

3. **What distance metrics are commonly used in KNN?**
   - Common metrics include **Euclidean distance** and **Manhattan distance**, which measure how far apart points are.

4. **What are the advantages and disadvantages of KNN?**
   - **Advantages**: Simple to understand and implement, works well with small datasets.
   - **Disadvantages**: Slow with large datasets and sensitive to noisy data.

5. **Can you explain how KNN can be used for both classification and regression tasks?**
   - In classification, KNN assigns a class label based on the majority vote of neighbors. In regression, it averages the values of neighbors to predict a continuous output.
