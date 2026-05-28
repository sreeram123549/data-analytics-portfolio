# Brazil's Ethanol Success: A Data-Driven Analysis

## Project Overview

This analysis explores 50 years of Brazil's ethanol industry journey (1975-2024) to understand the economic and environmental impact of biofuel adoption, with implications for India's energy policy.

**Duration:** 50 years | **Data Points:** 1975-2024 | **Focus Countries:** Brazil

---

## Key Findings

### Jobs & Economy
- **378K bioethanol jobs** created in 2024
- **474K agriculture sector jobs** in sugarcane production (63% of total)
- **751K total jobs** across the entire sugarcane-ethanol ecosystem

### Environmental Impact
- **828.7 Million tonnes CO2 avoided** since 1975 vs. gasoline baseline
- **32.5% reduction in air pollution** (PM 2.5) from 2011 to 2023 (30.29 → 20.44 μg/m³)
- **39-46% emission reduction** compared to pure gasoline vehicles

### Market Transformation
- Flex-fuel vehicles went from **0 to 79.9%** of new car sales by 2024
- **2015:** 25.6% vehicle sales decline (economic recession + political crisis)
- **2020:** COVID-19 impact, but recovery started 2021

---

## Data Sources

| Source | Data | Year |
|--------|------|------|
| Ministry of Petroleum & Natural Gas (Brazil) | Ethanol blending targets, CO2 formulas | 2024 |
| UNICA (Sugarcane Industries) | Ethanol & sugar production | 1980-2024 |
| Aguiar et al. (2024) | CO2 avoided (Life Cycle Assessment) | 1975-2022 |
| World Bank Open Data | Transport sector CO2 emissions | 1970-2022 |
| USDA FAS | Vehicle sales, ethanol production | 2003-2024 |
| Our World in Data | CO2 emissions profiles | 1970-2024 |

---

## Methodology

### Data Cleaning
- Removed outliers & invalid records
- Standardized date formats across sources
- Created Year Table for proper relationships in Power BI

### Data Modeling
- Star schema design with Year Table as central hub
- Relationships: All tables → Year Table (single source of truth)
- DAX calculations for aggregations & trends

### Analysis Approach
1. **Exploratory Data Analysis** — Identified patterns & anomalies
2. **Contextual Analysis** — Explained dips (2015 recession, 2020 pandemic)
3. **Comparative Analysis** — Brazil vs. USA vs. India potential
4. **Impact Assessment** — Jobs, emissions, market adoption

---

## Insights & Business Logic

### Timeline: How Brazil Built It (50 Years)
- **1975:** Proálcool program launched (oil crisis response)
- **1979:** Ethanol-compatible cars introduced
- **2003:** Flex-fuel vehicles arrived → production boom
- **2011-12:** 27% production drop (bad sugarcane harvest)
- **2015:** 25.6% vehicle sales decline (economic recession)
- **2020:** COVID-19 pandemic impact
- **2024:** Record 378K jobs, dominant market position

### Why This Matters for India

**Problems India faces (like Brazil did):**
-  Heavy air pollution (PM 2.5 levels among world's worst)
-  Crude oil imports costing crores annually
-  BUT: Sugar production capacity exists (UP, Maharashtra, Karnataka, Tamil Nadu)

**Brazil's solution (applicable to India):**
- Steady job creation in farming + manufacturing
- Measurable air quality improvements
- Reduced oil dependency
- Long-term infrastructure investment

**Important caveats:**
- Ethanol alone won't solve pollution → Need trees, better transport, stricter emission rules
- This took 50 years → Requires government commitment & consistency
- Water is India's constraint (unlike Brazil) → Need efficient farming methods

---

## Tools & Techniques Used

**Power BI:**
- Data modeling (star schema, relationships)
- DAX formulas for aggregations
- Interactive dashboards (7 pages)
- Drill-through capabilities

**SQL:**
- Data extraction & transformation
- Complex queries for validation
- Cleaning duplicate/invalid records

**Excel:**
- Pivot tables for quick analysis
- Data validation
- Calculations & assumptions documentation

---

## Dashboard Pages

1. **Cover** — KPI overview (378K jobs, 828.7M CO2, agriculture impact)
2. **Ethanol & Sugar Production** — Production trends 1980-2024
3. **CO2 Emissions by Biofuel** — Total emissions + biofuel context
4. **CO2 Impact** — CO2 avoided vs. production (direct correlation)
5. **Vehicle Sales by Fuel Type** — Flex-fuel dominance story (2003-2024)
6. **Air Pollution** — PM 2.5 decline (2011-2023)
7. **Employment** — Jobs created & sector breakdown



## Key Assumptions & Limitations

**Assumptions:**
- CO2 avoided calculated using Life Cycle Assessment (LCA) methodology
- Brazil's job model (0.14 jobs/1M tonnes) can estimate India's potential
- Employment data for 2008 shows total sector (not bioethanol-specific) due to data availability

**Limitations:**
- CO2 data available only through 2022 (2023-24 pending publication)
- Employment data has only 4 data points (2008, 2020, 2023, 2024)
- Brazil's climate/water resources differ from India's constraints

---
<img width="1920" height="1024" alt="Screenshot 2026-05-28 143339" src="https://github.com/user-attachments/assets/abd8e45b-035b-4838-a34d-43bc1b093a58" />
<img width="1906" height="1000" alt="Screenshot 2026-05-28 143414" src="https://github.com/user-attachments/assets/ef607290-5af3-4a49-9b1f-fdf0f83595a6" />
<img width="1903" height="1004" alt="Screenshot 2026-05-28 144327" src="https://github.com/user-attachments/assets/a712ebf0-5709-48c0-a1a5-d1657ea224a6" />
