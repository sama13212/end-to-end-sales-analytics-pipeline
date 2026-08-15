# Restaurant Sales Analytics — Databricks, PySpark, Spark SQL & Power BI

## Overview

An end-to-end restaurant sales analytics project analyzing **1,000,000 orders** across **6 branches in Egypt**.

The project covers data ingestion, data quality validation, feature engineering, business analysis using **PySpark and Spark SQL on Databricks**, and interactive visualization through a **Power BI dashboard**.

The goal is to transform raw transactional data into reliable business insights that can support decisions around branch performance, product categories, customer behavior, and sales trends.

---

## Business Problem

Restaurant businesses generate large volumes of transactional data across branches, products, customers, payment methods, and order types.

The objective of this project is to analyze restaurant order data and answer practical business questions such as:

* Which branches generate the highest revenue and order volume?
* Which categories perform best?
* How does performance differ between weekdays and weekends?
* Which payment methods and order types are most common?
* How do customer ratings vary across categories?
* What are the overall sales and customer metrics?

---

## Dataset

The dataset contains **1,000,000 restaurant orders** and **15 columns**.

### Main Fields

* `order_id`
* `order_date`
* `hour`
* `category`
* `item_name`
* `price`
* `quantity`
* `discount`
* `total_amount`
* `branch`
* `payment_method`
* `order_type`
* `customer_id`
* `rating`
* `is_weekend`

### Dataset Overview

| Metric              |     Value |
| ------------------- | --------: |
| Total Orders        | 1,000,000 |
| Columns             |        15 |
| Branches            |         6 |
| Categories          |         5 |
| Unique Customers    |   198,667 |
| Total Revenue       |  ~260.98M |
| Average Order Value |   ~260.98 |
| Average Rating      |      3.70 |

### Branches

* Cairo
* Giza
* Alexandria
* Tanta
* Mansoura
* Assiut

---

## Project Pipeline

```text
Raw CSV
   ↓
Databricks
   ↓
PySpark DataFrame
   ↓
Data Quality Validation
   ↓
Feature Engineering
   ↓
Spark SQL Analysis
   ↓
Delta Table
   ↓
Power BI Dashboard
```

---

## Technologies & Tools

### Python

Used for initial data exploration and supporting analysis.

### Pandas

Used for initial exploratory checks and understanding the dataset structure.

### PySpark

Used for:

* Loading the dataset
* Schema handling
* Data quality validation
* Duplicate and null checks
* Feature engineering
* Large-scale data processing

### Spark SQL

Used to answer business questions through SQL queries, including:

* Revenue by branch
* Revenue by category
* Order volume by branch
* Weekday vs. weekend performance
* Customer metrics
* Rating analysis

### Databricks

Used as the development and processing environment for the PySpark and Spark SQL workflow.


### Power BI

Used to create an interactive dashboard containing KPIs and multiple business-focused visualizations.

### Matplotlib

Used for supporting visualization during the analysis.

---

## Data Quality Validation

Before performing the analysis, the dataset was validated using PySpark.

The following checks were performed:

### Null Values

All 15 columns were checked for missing values.

**Result:** 0 null values found.

### Duplicate Records

The total row count was compared with the distinct row count.

```text
Total Rows:     1,000,000
Distinct Rows:  1,000,000
```

**Result:** No duplicate records found.

### Order ID Uniqueness

The number of unique `order_id` values was checked.

```text
Unique Order IDs: 1,000,000
```

**Result:** Every order has a unique ID.

---

## Data Processing & Feature Engineering

PySpark was used to process the dataset and derive additional time-based features from `order_date`.

The following fields were created:

* `year`
* `month`
* `day_name`

These features support time-based analysis and business comparisons.

The processed dataset was then registered as a temporary Spark SQL view and persisted as a Delta table.

---

## SQL Business Analysis

Spark SQL was used to answer practical business questions.

### Revenue & Order Performance

Analysis was performed across:

* Branches
* Categories
* Weekdays vs. weekends

Revenue calculations use `total_amount` because it represents the actual order value after considering quantity and discounts.

### Customer Analysis

The analysis includes:

* Total customers
* Distinct customers
* Average customer rating

### Operational Analysis

Additional breakdowns include:

* Payment methods
* Order types
* Product categories
* Branch performance

---

## Key Insights

Based on the analysis of the full dataset:

* **Cairo** is the highest-performing branch by order volume.
* **Grills (مشويات)** is the top-performing category by order volume and sales.
* The dataset contains **198,667 unique customers** across the six branches.
* The overall average customer rating is **3.70/5**.
* Total revenue across the dataset is approximately **260.98M**, with an average order value of approximately **260.98**.

> Revenue comparisons are based on `total_amount`, ensuring that quantity and discounts are reflected in the analysis.

---

## Power BI Dashboard

The project includes an interactive single-page Power BI dashboard designed to provide a high-level overview of restaurant performance.

### Dashboard Includes

* Total Orders
* Total Revenue
* Total Customers
* Items Sold
* Average Order Value
* Discount Rate
* Revenue by Branch
* Revenue by Category
* Revenue by Payment Method
* Revenue by Item
* Order Type Distribution
* Average Rating by Category
* Revenue Trend Over Time

### Dashboard Preview

*Add the final unfiltered dashboard screenshot here.*

```text
![Restaurant Sales Dashboard](images/dashboard_screenshot.png)
```

---

## Project Structure

```text
restaurant-sales-analytics/
│
├── notebooks/
│   └── restaurant_project.ipynb
│
├── dashboard/
│   └── restaurant_data.pbix
│
├── images/
│   └── dashboard_screenshot.png
│
└── README.md
```

---

## How to Run

### 1. Load the Dataset

Upload `restaurant1.csv` to a Databricks Volume or update the file path according to your environment.

### 2. Run the Notebook

Open:

```text
notebooks/restaurant_project.ipynb
```

Run the notebook from top to bottom using a Databricks environment with PySpark and Spark SQL support.

### 3. Explore the Dashboard

Open:

```text
dashboard/restaurant_data.pbix
```

using Power BI Desktop.

---

## Key Learnings

Through this project, I practiced:

* Working with a dataset containing **1 million records**
* Using PySpark for data processing and validation
* Writing Spark SQL queries to answer business questions
* Performing systematic data quality checks
* Creating time-based features
* Persisting processed data using Delta tables
* Building business-focused Power BI dashboards
* Translating raw transactional data into actionable insights

---

## Future Improvements

Potential improvements include:

* Adding deeper time-series analysis
* Adding more notebook visualizations
* Exploring the relationship between discounts and order performance
* Performing deeper customer behavior analysis
* Adding advanced SQL analysis such as ranking and window functions
* Expanding the Power BI dashboard with additional analytical pages

---

## Project Outcome

This project demonstrates an end-to-end analytics workflow starting from raw transactional data and ending with an interactive business intelligence dashboard.

It combines **Python, PySpark, Spark SQL, Databricks and Power BI** to transform and analyze **1,000,000 restaurant orders** and communicate the resulting business insights through interactive visualizations.

---

## Author

**Sama Ahmed**

Computer Science Student | Data Analyst Enthusiast

### Skills Demonstrated

`Python` `Pandas` `PySpark` `SQL` `Databricks` `Power BI` `Data Analytics`
