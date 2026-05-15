 Data Analytics Portfolio

Hi, I'm Sreeram — an aspiring data analyst passionate about working with real-world data to uncover meaningful insights. This portfolio showcases projects where I practice data cleaning, analysis, and visualization using SQL and Power BI.

 ##Projects

| Project | Tools | Description |
|--------|-------|-------------|
| [Oregon Transportation Expenditures (2022–2024)](#oregon-transportation-expenditures-2022-2024) | SQL, Power BI | Cleaned and analysed 37,000+ rows of government expenditure data from Oregon's Department of Transportation across 3 fiscal years. Identified data quality issues, standardised formats, and built an interactive Power BI dashboard. |

---

 ##Transportation Expenditures (2022–2024)

### Project Overview

This project focuses on cleaning, transforming, and analysing a government transportation expenditure dataset using SQL. The dataset contains expenditure transactions across multiple fiscal years, departments, vendors, expenditure classes, and budget categories.

Primary objectives:
- Clean and standardise raw transactional data
- Handle duplicates and inconsistent values
- Perform string transformations and conditional data parsing
- Prepare the dataset for exploratory analysis and visualization
- Generate analytical insights using SQL aggregation techniques
- Build an interactive Power BI dashboard

---

# Dataset Information

- **Source:** [data.gov](https://data.gov) — Oregon Agency Expenditures Multi-Year Report
- **Agency:** Department of Transportation (Agency #730)
- **Years covered:** 2022, 2023, 2024
- **Total rows:** 37,611
- **Columns:** Fiscal Year, Agency, Budget Class, Expenditure Class, Vendor, Expense, Vendor State

---

# Data Cleaning Steps

## 1. Duplicate Detection & Removal
Identified and removed duplicate records while preserving original transactional integrity.

**Concepts used:** `ROW_NUMBER() OVER(PARTITION BY ...)`, CTEs, conditional duplicate filtering

---

### 2. Column Name Standardisation
Renamed columns to follow consistent naming conventions — converted to lowercase and removed special characters such as `#` and spaces.

Example:
- `BUDGET CLASS #` → `budget_class_id`
- `EXPEND CLASS` → `expend_class`

**Concepts used:** Column aliasing, naming conventions

---

#### 3. Agency Name Formatting
Corrected the agency name format from reverse order to standard convention.

Example: `TRANSPORTATION, DEPT OF` → `DEPT OF TRANSPORTATION`

**Concepts used:** `UPDATE`, string standardisation

---

#### 4. Spelling Correction
Fixed a typo in the Budget Class column.

Example: `PUBLIC EMPLOYES' RETIREMENT SYSTEM` → `PUBLIC EMPLOYEES' RETIREMENT SYSTEM`

**Concepts used:** `UPDATE`, `WHERE` filtering

---

#### 5. Expense Value Rounding
Standardised expense values to 1 decimal place for consistent financial reporting.

**Concepts used:** `ROUND()`, `UPDATE`

---

#### 6. Vendor Name Parsing & Transformation
The vendor column contained mixed entity types — personal names, departments, agencies, and organisations. Personal names followed a `LASTNAME, FIRSTNAME MIDDLENAME` pattern.

Solution: Implemented conditional string parsing to extract first names from personal-name formatted vendors while preserving organisation names unchanged. A new column `clean_vendor` was created to preserve the original raw data.

Concepts used: `CASE WHEN`, `LOCATE()`, `SUBSTRING()`, `TRIM()`, nested string functions

Example: `CROOK, GEOFFREY STEPHEN` → `GEOFFREY`

---

#### 7. NULL Value Handling
Replaced NULL values in the vendor_state column with `'UNKNOWN'` for reporting clarity.

Concepts used: `UPDATE`, `IS NULL`

---

Key Findings

Total expenditure by year:

| Fiscal Year | Total Spend |
|-------------|-------------|
| 2022 | $1.87 Billion |
| 2023 | $1.81 Billion |
| 2024 | $1.84 Billion |

**Top 3 expenditure categories (2022–2024 combined):**
1. Agency Program Related Services — **$2.30 Billion**
2. Professional Services (Non-IT) — **$813 Million**
3. Distribution to Other Governments — **$550 Million**

**Top vendor states by spend:**
1. Oregon (OR) — $3.99 Billion
2. Washington (WA) — $486 Million
3. California (CA) — $303 Million

---

### Power BI Dashboard

An interactive dashboard was built on top of the cleaned dataset with the following features:

- **KPI summary visuals** — total expenditure by fiscal year
- **Horizontal bar chart** — top expenditure categories ranked by spend
- **Treemap** — budget class distribution by percentage contribution
- **Filled map** — geographic expenditure distribution by vendor state
- **Fiscal year slicer** — dynamic filtering across all visuals (2022–2024)
- **Cross-filtering** — selecting a state dynamically recalculates all charts

**Design decisions:**
- Replaced pie chart with treemap for budget distribution — pie chart became overcrowded with too many categories
- Replaced KPI trend axis with executive-style summary cards — limited yearly data points made the trend unclear

---

### SQL Concepts Used

- Window Functions — `ROW_NUMBER()`, `PARTITION BY`
- CTEs (Common Table Expressions)
- String Functions — `TRIM()`, `LOWER()`, `SUBSTRING()`, `LOCATE()`
- Conditional Logic — `CASE WHEN`
- Aggregation — `SUM()`, `MAX()`, `COUNT()`
- Grouping & Filtering — `GROUP BY`, `HAVING`, `ORDER BY`
- Data Modification — `UPDATE`, `WHERE`

---

## Skills

- **SQL** — data cleaning, aggregations, joins, window functions, CTEs
- **Power BI** — dashboards, slicers, cross-filtering, map visuals, treemaps
- **Data Cleaning** — handling nulls, fixing inconsistencies, standardising formats
- **Tools** — SQLiteOnline, Power BI Desktop, GitHub

---

## About the Data

All datasets used in this portfolio are sourced from publicly available government data at [data.gov](https://data.gov). No sensitive or private data is used.

---



[PowerBI_Dashboard_Documentation.docx](https://github.com/user-attachments/files/27796982/PowerBI_Dashboard_Documentation.docx)

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/42ddcd97-d97f-4696-89f4-dcc5c207c23e" />



## Connect

Feel free to reach out or follow my progress as I continue building this portfolio.

- GitHub: [sreeram123549](https://github.com/sreeram123549)
