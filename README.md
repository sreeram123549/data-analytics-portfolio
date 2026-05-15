Transportation Expenditures Data Cleaning & Analysis (SQL Project)
Project Overview

This project focuses on cleaning, transforming, and analyzing a large government transportation expenditure dataset using MySQL. The dataset contains expenditure transactions across multiple fiscal years, departments, vendors, expenditure classes, and budget categories.

The primary objective of this project was to:

Clean and standardize raw transactional data
Handle duplicates and inconsistent values
Perform string transformations and conditional data parsing
Prepare the dataset for exploratory analysis and visualization
Generate analytical insights using SQL aggregation techniques
Dataset Information

The dataset includes:

Fiscal Year
Department / Agency Information
Budget & Expenditure Classes
Vendor Information
Expense Amounts
Vendor State Information

The project was performed on a reduced portfolio-friendly dataset focused on transportation-related expenditures from 2022–2024.

Data Cleaning Steps Performed
1. Duplicate Detection & Removal
Identified duplicate records using:
ROW_NUMBER()
Common Table Expressions (CTEs)
Window Functions
Removed duplicate rows while preserving original transactional integrity
Concepts Used
ROW_NUMBER() OVER(PARTITION BY ...)
CTEs
Conditional duplicate filtering
2. Column Name Standardization
Renamed columns to follow consistent naming conventions
Converted column names to lowercase
Removed problematic special characters from column names
Example
BUDGET CLASS # → budget_type
EXPEND CLASS → expend_type
3. Text Standardization

Performed text cleaning operations including:

Converting values to lowercase
Removing leading/trailing spaces using TRIM()
Standardizing inconsistent categorical values
Concepts Used
LOWER()
TRIM()
UPDATE
4. Vendor Name Parsing & Transformation

The vendor column contained mixed entity types:

Personal names
Departments
Agencies
Hotels
Organizations
Challenge

Some vendor names followed patterns like:

lastname, firstname middleinitial
Solution

Implemented conditional string parsing logic to:

Extract only first names from personal-name formatted vendors
Preserve organization/vendor names unchanged
SQL Functions Used
CASE WHEN
LOCATE()
SUBSTRING()
SUBSTRING_INDEX()
Nested string functions
Example Transformation
case, nicholas b
→
nicholas

A new column (clean_vendor) was created to preserve original raw vendor data.

5. Conditional Data Cleaning

Applied transformations selectively using conditional logic:

Cleaned only rows matching name patterns
Preserved non-person entities such as:
Departments
Agencies
Organizations
Concepts Used
CASE
Conditional transformations
Pattern-based cleaning logic
Exploratory Data Analysis (EDA)

After cleaning, exploratory analysis was performed to identify spending trends and vendor insights.

Analyses Performed
Top expenditure classes
Highest spending vendors by fiscal year
Largest expenditure transactions
Vendor expenditure aggregation
Department-level spending analysis
SQL Concepts Used
GROUP BY
SUM()
MAX()
ORDER BY
LIMIT
Aggregation queries
Key SQL Skills Demonstrated
Data Cleaning
Window Functions
Duplicate Handling
Conditional Updates
String Parsing
Data Standardization
Data Analysis
Aggregation
Ranking Queries
Filtering
Exploratory Analysis
Trend Identification
---

Imported the above cleaned data onto POWER BI DESKTOP for DASHBOARD creation

[PowerBI_Dashboard_Documentation.docx](https://github.com/user-attachments/files/27796982/PowerBI_Dashboard_Documentation.docx)

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/42ddcd97-d97f-4696-89f4-dcc5c207c23e" />



## Connect

Feel free to reach out or follow my progress as I continue building this portfolio.

- GitHub: [sreeram123549](https://github.com/sreeram123549)
