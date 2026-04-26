# E-Commerce-Project-02
This project simulates a real-world e-commerce data analyst workflow using SQL on a messy inventory dataset inspired by Zepto product listings.


# Project Report: Zepto E-Commerce Inventory SQL Analysis

## 📄 Executive Summary
This project simulates the end-to-end workflow of a Data Analyst within the e-commerce and retail sectors. By leveraging a real-world dataset, the analysis demonstrates the transformation of "messy" raw inventory data into a structured, clean, and actionable business asset. The primary objective is to replicate the logic used by major platforms to manage stock, optimize pricing strategies, and derive strategic insights from complex product listings.

---

## 📊 Dataset & Technical Landscape
The data utilized in this study was sourced from Kaggle, consisting of product listings originally scraped from Zepto. The dataset accurately mirrors the complexity of actual e-commerce systems; for instance, it contains duplicate product names representing unique **SKUs (Stock Keeping Units)** because items often appear in various package sizes or weights to maximize visibility on the consumer-facing app.

### Data Dictionary
The following attributes were handled and processed within the PostgreSQL environment:


Description of dataset columns : 

 sku_id : Synthetic Primary Key for unique product identification. 
 category : Broad classification (e.g., Fruits, Snacks, Beverages). 
 name : Product name as it appears on the application. 
 mrp : Maximum Retail Price (converted from paise to ₹). 
 discountPercent : The percentage reduction applied to the product. 
 availableQuantity : Current stock units available in the warehouse. 
 weightInGms : Physical weight of the item for logistics tracking. 
outOfStock : Boolean flag indicating current availability. 


## ⚙️ Methodological Workflow

### 1. Database Architecture & Integration
The project began with the construction of a robust schema. Using **PostgreSQL**, a dedicated table was designed with specific data types to ensure data integrity, such as `NUMERIC` for financial figures and `BOOLEAN` for stock flags. The ingestion process involved handling CSV files via **pgAdmin**, with specific attention paid to **UTF-8 encoding** to ensure special characters and formatting remained intact during the import.

### 2. Exploratory Data Analysis (EDA)
Before manipulation, the data underwent a rigorous exploration phase. This involved auditing the total record count, identifying null values across all columns, and assessing the distribution of categories. By comparing in-stock versus out-of-stock ratios, we established a baseline understanding of inventory health and identified the frequency of multi-SKU product listings.

### 3. Data Refinement & Normalization
Real-world data is rarely pristine. A critical phase of this project involved data cleaning and normalization, specifically:
* **Logical Filtering:** Identifying and removing records where the MRP or discounted selling price was zero or invalid.
* **Currency Normalization:** A vital step where prices were converted from **paise to rupees** to ensure the data is readable and aligned with standard business reporting.

### 4. Strategic Business Intelligence
The final stage of the workflow involved writing complex SQL queries to solve specific business problems and extract value. Key analyses included:
* **Value Assessment:** Identifying the "best-value" products based on the highest discount percentages.
* **Revenue Protection:** Tracking high-value items that are currently out of stock to minimize potential lost sales.
* **Categorical Performance:** Measuring the total inventory weight and estimating potential revenue per category.
* **Logistics Optimization:** Grouping products into "Low," "Medium," and "Bulk" categories based on weight to assist in distribution and delivery planning.

