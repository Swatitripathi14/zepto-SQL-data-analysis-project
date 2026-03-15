🛒 Zepto E-commerce SQL Data Analyst Portfolio Project

This is a complete, real-world Data Analyst portfolio project based on an e-commerce inventory dataset scraped from Zepto, one of India’s fastest-growing quick-commerce startups.

The project simulates how data analysts work with real datasets, from raw data exploration to extracting business insights using SQL.

This project is perfect for:

📊 Data Analyst aspirants building a portfolio project

📚 Beginners learning SQL with real datasets

💼 Students preparing for data analyst interviews

📌 Project Overview

The goal of this project is to simulate how data analysts in e-commerce or retail companies use SQL to:

✅ Build an inventory database

✅ Perform Exploratory Data Analysis (EDA)

✅ Clean messy data

✅ Write business-driven SQL queries

✅ Extract insights related to pricing, inventory, stock availability, and revenue

📁 Dataset Overview

The dataset was sourced from Kaggle and scraped from Zepto’s product listings.

Each row represents a unique SKU (Stock Keeping Unit).

Duplicate product names may exist because the same product can appear in different:

package sizes

weights

discounts

categories

This reflects how real e-commerce product catalogs work.

🧾 Dataset Columns
Column	Description
sku_id	Unique identifier for each product
name	Product name
category	Product category (Snacks, Fruits, Beverages, etc.)
mrp	Maximum Retail Price
discountPercent	Discount applied on MRP
discountedSellingPrice	Final selling price after discount
availableQuantity	Number of units available
weightInGms	Product weight in grams
outOfStock	Indicates whether product is out of stock
quantity	Units per package
🔧 Project Workflow
1️⃣ Database & Table Creation

Create the SQL table:

CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);
2️⃣ Data Import

The dataset was imported using pgAdmin CSV import.

Alternatively, you can use:

\copy zepto(category,name,mrp,discountPercent,availableQuantity,
discountedSellingPrice,weightInGms,outOfStock,quantity)
FROM 'data/zepto_v2.csv'
WITH (FORMAT csv, HEADER true, DELIMITER ',', QUOTE '"', ENCODING 'UTF8');
3️⃣ Data Exploration

Performed exploratory data analysis to understand the dataset:

Count total number of records

View sample data

Check null values

Identify unique categories

Compare in-stock vs out-of-stock products

Detect duplicate product names

4️⃣ Data Cleaning

Steps performed:

Removed rows where MRP or selling price = 0

Converted price from paise to rupees

Cleaned inconsistent values

5️⃣ Business Insights

SQL queries were written to answer real business questions:

Top 10 best-discounted products

High-MRP products that are out of stock

Potential revenue per category

Expensive products with low discount

Top categories offering highest discounts

Price per gram for value comparison

Product grouping by weight category

Total inventory weight per category

🛠️ How to Use This Project
1️⃣ Clone the Repository
git clone https://github.com/yourusername/zepto-sql-analysis.git
cd zepto-sql-analysis
2️⃣ Open the SQL File

The SQL file includes:

Table creation

Data exploration queries

Data cleaning queries

Business insight queries

3️⃣ Load Dataset into PostgreSQL

Steps:

Create a database

Run the SQL table creation script

Import the dataset using pgAdmin

🧑‍💻 Tools Used

SQL (PostgreSQL)

pgAdmin

Kaggle Dataset

GitHub

📊 Skills Demonstrated

SQL Queries

Data Cleaning

Data Exploration

Business Analysis

Inventory Data Analysis

Data Analyst Workflow
