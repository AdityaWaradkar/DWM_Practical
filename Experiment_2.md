
# Experiment 2: Implementation of All Dimension Tables and Fact Table Based on Experiment 1 Case Study

## 1. SQL Code for Creating the Star Schema

Below is the SQL code for creating the **dimension tables** and the **fact table** for the retail store's data warehouse.

### a. Creating the Dimension Tables

- **Product Dimension Table**:

```sql
CREATE TABLE Product (
    product_key INT PRIMARY KEY AUTO_INCREMENT,
    product_name VARCHAR(255),
    category VARCHAR(255),
    brand VARCHAR(255),
    price DECIMAL(10, 2)
);
```

- **Time Dimension Table**:

```sql
CREATE TABLE Time (
    time_key INT PRIMARY KEY AUTO_INCREMENT,
    date DATE,
    day_of_week VARCHAR(50),
    month VARCHAR(50),
    quarter VARCHAR(50),
    year INT
);
```

- **Store Dimension Table**:

```sql
CREATE TABLE Store (
    store_key INT PRIMARY KEY AUTO_INCREMENT,
    store_name VARCHAR(255),
    city VARCHAR(100),
    state VARCHAR(100),
    region VARCHAR(100)
);
```

- **Customer Dimension Table**:

```sql
CREATE TABLE Customer (
    customer_key INT PRIMARY KEY AUTO_INCREMENT,
    customer_name VARCHAR(255),
    gender VARCHAR(10),
    age_group VARCHAR(50),
    income_level VARCHAR(50)
);
```

### b. Creating the Fact Table (Sales_Fact)

- **Sales Fact Table**:

```sql
CREATE TABLE Sales_Fact (
    sales_id INT PRIMARY KEY AUTO_INCREMENT,
    time_key INT,
    product_key INT,
    store_key INT,
    customer_key INT,
    sales_amount DECIMAL(10, 2),
    quantity_sold INT,
    FOREIGN KEY (time_key) REFERENCES Time(time_key),
    FOREIGN KEY (product_key) REFERENCES Product(product_key),
    FOREIGN KEY (store_key) REFERENCES Store(store_key),
    FOREIGN KEY (customer_key) REFERENCES Customer(customer_key)
);
```

### c. Sample Data Insertion

Now, insert some sample data into the tables to visualize the data warehouse.

- **Inserting Data into Product Dimension**:

```sql
INSERT INTO Product (product_name, category, brand, price)
VALUES 
('Laptop', 'Electronics', 'HP', 50000),
('Mobile', 'Electronics', 'Samsung', 25000),
('Tablet', 'Electronics', 'Apple', 30000);
```

- **Inserting Data into Time Dimension**:

```sql
INSERT INTO Time (date, day_of_week, month, quarter, year)
VALUES 
('2023-10-01', 'Sunday', 'October', 'Q4', 2023),
('2023-10-02', 'Monday', 'October', 'Q4', 2023);
```

- **Inserting Data into Store Dimension**:

```sql
INSERT INTO Store (store_name, city, state, region)
VALUES 
('Store A', 'Mumbai', 'Maharashtra', 'West'),
('Store B', 'Delhi', 'Delhi', 'North');
```

- **Inserting Data into Customer Dimension**:

```sql
INSERT INTO Customer (customer_name, gender, age_group, income_level)
VALUES 
('John Doe', 'Male', '25-34', 'Medium'),
('Jane Smith', 'Female', '35-44', 'High');
```

- **Inserting Data into Sales Fact Table**:

```sql
INSERT INTO Sales_Fact (time_key, product_key, store_key, customer_key, sales_amount, quantity_sold)
VALUES 
(1, 1, 1, 1, 50000, 1),
(2, 2, 2, 2, 25000, 1);
```

---

## 2. Explanation of Tables

- **Product Dimension**: Contains details about products sold, such as name, category, brand, and price.
- **Time Dimension**: Stores information about the time at which the sale occurred (e.g., day, month, quarter, year).
- **Store Dimension**: Holds data about the store location (store name, city, state, and region).
- **Customer Dimension**: Contains customer-related details (name, gender, age group, and income level).
- **Sales Fact Table**: Stores the transactional data, such as the total sales amount and quantity sold. It references the dimension tables using foreign keys.

---

## 3. Viva Questions and Key Notes

### a. What is a Star Schema?
- A **star schema** is a type of dimensional model where a **central fact table** is connected to multiple dimension tables, forming a star-like structure. It is simple and de-normalized for fast querying.

### b. What are Fact and Dimension Tables?
- **Fact Table**: Holds measurable, quantitative data (e.g., sales amount, quantity sold). It contains foreign keys pointing to dimension tables.
- **Dimension Table**: Stores descriptive data (e.g., product details, store location) that provide context for the fact table data.

### c. Explain the Purpose of Foreign Keys in the Fact Table:
- Foreign keys link the **fact table** to the **dimension tables**, creating relationships between the transactional data and its descriptive attributes.

### d. Why Use SQL for Implementing a Data Warehouse?
- SQL is commonly used for implementing data warehouses because it is efficient for managing relational databases, supports complex queries, and enables the creation of both fact and dimension tables.

### e. What is the Purpose of OLAP in Data Warehouses?
- **OLAP (Online Analytical Processing)** helps analyze large datasets by enabling complex queries to aggregate and summarize data across multiple dimensions. It is used for decision support and business intelligence.

### f. What’s the Difference Between Star Schema and Snowflake Schema?
- **Star Schema**: Simplified, de-normalized, fast for querying.
- **Snowflake Schema**: More normalized, reduced data redundancy, but more complex.

### g. What is the Role of the Fact Table in Analysis?
- The fact table is at the heart of the analysis in a data warehouse, containing the key measurements and metrics (e.g., total sales, quantity sold) for decision-making.

---

## 4. Additional Notes for Practical

- **Data Normalization**: Star schema keeps the dimensions de-normalized, while the snowflake schema further normalizes them.
- **Primary Key**: Each dimension table has a primary key (e.g., `product_key`), which uniquely identifies each record.
- **Foreign Key Relationships**: Fact tables rely on foreign key relationships to link to dimensions.