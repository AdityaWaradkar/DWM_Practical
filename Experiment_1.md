
# Experiment 1: Case Study on Building a Data Warehouse/Data Mart

## 1. Problem Statement:

Design a Data Warehouse (or Data Mart) for a retail store chain that wants to analyze sales data. 
The store wants to track the sales performance by different dimensions such as **Time**, **Product**, **Store Location**, and **Customer**. 
The goal is to allow the company to get insights into sales patterns, which could help with making informed decisions about marketing strategies, 
stocking products, and predicting future sales.

The retail company has different branches across various cities, and they sell multiple categories of products. 
The company needs to track and report on:

- Total sales per product across time.
- Sales performance by store and city.
- Customer purchase behavior (e.g., frequent customers, customer demographics).

To accomplish this, a Data Warehouse will be built using a dimensional model (star and snowflake schema) for analyzing sales over time.

## 2. Dimensional Modeling:

Dimensional modeling is a technique for designing databases that support OLAP (Online Analytical Processing). 
There are two main schemas commonly used:

- **Star Schema**
- **Snowflake Schema**

### a. Star Schema Design:

The star schema is the simplest type of dimensional model. It consists of **fact tables** and **dimension tables**.

#### **Fact Table: Sales_Fact**

The fact table stores quantitative data, such as total sales. It also contains foreign keys to dimension tables.

| Fact Table   | Description                        |
|--------------|------------------------------------|
| **sales_id** (PK) | Unique sales transaction ID        |
| **time_key** (FK) | Links to the Time Dimension        |
| **product_key** (FK) | Links to the Product Dimension     |
| **store_key** (FK) | Links to the Store Dimension      |
| **customer_key** (FK) | Links to the Customer Dimension   |
| **sales_amount** | Total sales amount (Measure) |
| **quantity_sold** | Quantity of products sold (Measure) |

#### **Dimension Tables:**
Dimension tables contain descriptive attributes (context of the analysis).

- **Product Dimension**
    | product_key (PK) | product_name | category | brand | price |

- **Time Dimension**
    | time_key (PK) | date | day_of_week | month | quarter | year |

- **Store Dimension**
    | store_key (PK) | store_name | city | state | region |

- **Customer Dimension**
    | customer_key (PK) | customer_name | gender | age_group | income_level |

#### **Star Schema Diagram:**
- The central **Fact Table (Sales_Fact)** connects to the surrounding dimension tables (**Product**, **Time**, **Store**, **Customer**) forming a "star."

### b. Snowflake Schema Design:

The **snowflake schema** is a normalized version of the star schema. In this schema, dimensions are broken down into sub-dimensions.

#### Changes from Star Schema:
- The **Product Dimension** might be normalized by splitting **Category** and **Brand** into separate tables.

#### Example:
- **Product Dimension**: | product_key (PK) | product_name | category_key (FK) | brand_key (FK) | price |
- **Category Table**: | category_key (PK) | category_name |
- **Brand Table**: | brand_key (PK) | brand_name |

The rest of the tables remain the same.

#### **Snowflake Schema Diagram:**
- The **Fact Table (Sales_Fact)** connects to dimension tables, but some dimensions are further normalized into sub-dimensions like **Category** and **Brand** in the Product Dimension.

## 3. Viva Notes for Experiment:

### What is a Data Warehouse?
- A **Data Warehouse** is a centralized repository for storing large amounts of data from multiple sources. It is used for reporting and analysis.

### What is a Data Mart?
- A **Data Mart** is a subset of a data warehouse, focused on a specific area like sales or marketing. It is a smaller, more specialized version of a data warehouse.

### Difference Between Star and Snowflake Schema:
- **Star Schema**: Simpler, de-normalized structure, where dimensions are not broken into sub-tables.
- **Snowflake Schema**: More normalized, with dimension tables split into additional tables. It reduces redundancy but increases complexity.

### Why Use Dimensional Modeling?
- Dimensional modeling helps organize data for better querying and reporting in OLAP systems, focusing on **measures** (e.g., sales, profit) and **dimensions** (e.g., time, product).

### Fact vs. Dimension Tables:
- **Fact Table**: Contains measurable data, such as sales amounts or quantities.
- **Dimension Table**: Contains descriptive data, such as product details or customer information, used for filtering and analyzing the facts.

### Why Use a Star Schema?
- The star schema is widely used because of its simplicity and ease of querying. It offers fast response times for complex queries.

### Why Use a Snowflake Schema?
- A snowflake schema is useful when there is a need for data normalization, as it reduces redundancy and data anomalies but increases join complexity.