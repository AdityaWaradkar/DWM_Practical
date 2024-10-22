
# Experiment 3: Implementation of OLAP Operations: Slice, Dice, Rollup, Drilldown, and Pivot

This experiment focuses on implementing various **OLAP (Online Analytical Processing)** operations such as **Slice**, **Dice**, **Rollup**, **Drilldown**, and **Pivot** based on the data warehouse designed in Experiment 1.

## 1. OLAP Operations:

### a. **Slice:**
The **Slice** operation selects a single dimension from a given cube, resulting in a sub-cube.

#### Example SQL Query (Slicing by a specific year):
```sql
SELECT product_name, store_name, SUM(sales_amount) AS total_sales
FROM Sales_Fact
JOIN Time ON Sales_Fact.time_key = Time.time_key
JOIN Product ON Sales_Fact.product_key = Product.product_key
JOIN Store ON Sales_Fact.store_key = Store.store_key
WHERE Time.year = 2023
GROUP BY product_name, store_name;
```

In this example, the **Slice** operation focuses on the **year 2023**, extracting sales data only for that year.

---

### b. **Dice:**
The **Dice** operation selects two or more dimensions from a cube to create a sub-cube.

#### Example SQL Query (Dicing for a specific year and product category):
```sql
SELECT product_name, store_name, SUM(sales_amount) AS total_sales
FROM Sales_Fact
JOIN Time ON Sales_Fact.time_key = Time.time_key
JOIN Product ON Sales_Fact.product_key = Product.product_key
JOIN Store ON Sales_Fact.store_key = Store.store_key
WHERE Time.year = 2023 AND Product.category = 'Electronics'
GROUP BY product_name, store_name;
```

Here, the **Dice** operation focuses on sales data for **year 2023** and **Electronics** products.

---

### c. **Rollup:**
The **Rollup** operation performs aggregation along a hierarchy of dimensions, such as summarizing sales by time (year, quarter, month).

#### Example SQL Query (Rolling up from month to quarter):
```sql
SELECT Time.quarter, Product.category, SUM(sales_amount) AS total_sales
FROM Sales_Fact
JOIN Time ON Sales_Fact.time_key = Time.time_key
JOIN Product ON Sales_Fact.product_key = Product.product_key
GROUP BY Time.quarter, Product.category;
```

In this case, **Rollup** aggregates the sales from **month** to the **quarter** level.

---

### d. **Drilldown:**
The **Drilldown** operation is the reverse of Rollup, allowing you to navigate from higher levels of data (e.g., year) to more detailed levels (e.g., month).

#### Example SQL Query (Drilling down from quarter to month):
```sql
SELECT Time.month, Product.category, SUM(sales_amount) AS total_sales
FROM Sales_Fact
JOIN Time ON Sales_Fact.time_key = Time.time_key
JOIN Product ON Sales_Fact.product_key = Product.product_key
WHERE Time.quarter = 'Q4'
GROUP BY Time.month, Product.category;
```

Here, **Drilldown** breaks down data for **Q4** into **months**.

---

### e. **Pivot:**
The **Pivot** operation rotates the data, providing a different view of the data by transposing rows into columns or vice versa.

#### Example SQL Query (Pivoting sales data by product and store):
```sql
SELECT Product.product_name,
       SUM(CASE WHEN Store.store_name = 'Store A' THEN sales_amount ELSE 0 END) AS store_A_sales,
       SUM(CASE WHEN Store.store_name = 'Store B' THEN sales_amount ELSE 0 END) AS store_B_sales
FROM Sales_Fact
JOIN Product ON Sales_Fact.product_key = Product.product_key
JOIN Store ON Sales_Fact.store_key = Store.store_key
GROUP BY Product.product_name;
```

In this query, the **Pivot** operation compares sales for **Store A** and **Store B** across different products.

---

## 2. Viva Notes for OLAP Operations:

### What is OLAP?
- **OLAP (Online Analytical Processing)** is a category of software tools that provides analysis of data stored in a data warehouse. OLAP operations are used to perform complex queries on large volumes of data.

### What are the common OLAP operations?
- **Slice**: Extracts a subset of data along one dimension.
- **Dice**: Selects a sub-cube by choosing two or more dimensions.
- **Rollup**: Aggregates data along a hierarchy, such as from months to quarters.
- **Drilldown**: Breaks down aggregated data into finer levels, such as from quarters to months.
- **Pivot**: Rotates the data to provide a different perspective, often by swapping rows and columns.

### Why are OLAP operations useful?
- OLAP operations are essential for analyzing data in a multidimensional way, enabling decision-makers to view data from different perspectives, such as by time, product, or store.

---