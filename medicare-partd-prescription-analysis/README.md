Medicare Part D — Prescription Drug Analysis (2018–2023)
An end-to-end data analytics project examining prescription drug utilization and spending patterns among elderly Medicare beneficiaries (age 65+) across the 50 US states, covering the years 2018, 2021, and 2023.
Tools: Microsoft Excel (data cleaning) · Tableau Public (visualization)
Data Source: CMS Medicare Part D Prescribers by Geography and Drug — data.cms.gov
Live Dashboard: View on Tableau Public
________________________________________
Background
Medicare is the US federal health insurance program primarily for Americans aged 65 and older. Medicare Part D covers prescription drugs filled at pharmacies. This dataset, published by the Centers for Medicare & Medicaid Services (CMS), aggregates all Part D prescription claims by state and drug for each fiscal year — covering approximately 78.5% of all Medicare beneficiaries.
Each row in the dataset represents one state × drug combination for a given year (e.g., California + Eliquis, 2023), recording the total claims, total drug cost, beneficiary counts, and drug category flags.
________________________________________
Questions Explored
1.	Which drugs drive the highest Medicare Part D spending, and has the ranking shifted from 2018 to 2023?
2.	How has total drug spending changed relative to total prescription volume from 2018 to 2023?
3.	How does prescription intensity vary across states for elderly beneficiaries?
4.	How has opioid prescribing among elderly Medicare patients changed over the five-year window?
________________________________________
Key Findings

•	Eliquis (apixaban) is the single most expensive drug in Medicare Part D, accounting for the largest share of total drug cost in 2023. Blood thinners and diabetes medications dominate the top 10 by cost — reflecting the chronic disease burden of the elderly population.
•	Total drug spending grew significantly from 2018 to 2023 while total claims remained relatively flat. This gap indicates that cost per prescription is rising — driven by the increasing share of expensive brand-name specialty drugs rather than higher prescription volume.
•	Opioid prescribing among elderly Medicare patients declined approximately 16% from 2018 to 2023 — from ~70 million claims in 2018 to ~59 million in 2023. The sharpest drop occurred between 2018 and 2021, coinciding with tightened CDC prescribing guidelines. The rate of decline slowed between 2021 and 2023, suggesting the policy impact has largely plateaued.
•	Geographic variation in prescribing intensity exists across states, measured by claims per beneficiary. Some states show meaningfully higher prescription rates per elderly patient than others, reflecting differences in prescribing culture, access to care, and patient demographics.
________________________________________
Dashboard
The interactive dashboard contains four views:

Map — Age 65+ Claims	Choropleth map of Medicare Part D claims per beneficiary across 50 states. Click a state to filter the Top 10 Drugs chart.
Top 10 Drugs by Cost (2023)	Horizontal bar chart of the 10 highest-cost brand-name drugs. Responds to state selection on the map.
Trend — Cost vs Claims (2018–2023)	Combo bar + line chart showing total drug cost (bars) against total claims (line) across three years.
Opioid Trend (2018–2023)	Stacked bar chart showing opioid prescription claims by state for the top 10 opioid-prescribing states across three years.
Dashboard interaction: Clicking a state on the map filters the Top 10 Drugs chart to that state's data, enabling state-level drug spending exploration.
________________________________________
Data
File	Year	Rows	Source
Year_2018_clean.xlsx	2018	107,941	CMS MUP_DPR_RY21_P04_V10_DY18_Geo
Year_2021_clean.xlsx	2021	107,511	CMS MUP_DPR_RY23_P04_V10_DY21_Geo
Year_2023_clean.xlsx	2023	106,907	CMS MUP_DPR_RY25_P04_V10_DY23_Geo
Combined dataset: 322,359 rows × 21 columns after cleaning and union.
Raw data is publicly available at data.cms.gov.
________________________________________
Data Cleaning
1. Schema reconciliation across three years
CMS uses inconsistent column naming across release years. Key mismatches resolved:
2018 / 2021	2023	Resolution
Brand_name	Brand Name	Standardized to Brand Name
Generic_Name	Generic Name	Standardized to Generic Name
Total_Claims	Total Claims	Standardized to Total Claims
Total Benefeceries	Total Benefeceries	Corrected to Total Beneficiaries (all files)
All 21 columns were renamed to a consistent, human-readable format (e.g., Prscrbr_Geo_Desc → State, GE65_Tot_Clms → Age 65+ Claims, Opioid_Drug_Flag → Is Opioid).
2. Geographic filtering
Scope restricted to the 50 US states only. Removed:
•	National-level aggregate rows (used only for validation, not analysis)
•	Armed Forces entries (3 rows)
•	US territories (Puerto Rico, Virgin Islands, Northern Mariana Islands, etc.)
•	Foreign Country entries
•	Rows with unknown prescriber state (332 rows, 0.3% of dataset)
3. Redundant columns removed
•	Prscrbr_Geo_Lvl (Geography Level) — dropped after filtering to states only; became a constant
•	Prscrbr_Geo_Cd (FIPS code) — dropped as redundant with state name; also absent from 2023 file
4. Suppression flags
CMS suppresses beneficiary counts below 11 for privacy, indicated by blank cells. Per CMS methodology:
•	Suppressed cells in Age 65+ Claims, Age 65+ Drug Cost, and Age 65+ Beneficiaries were retained as blank (not imputed, not dropped)
•	Rows with suppressed total claims are excluded by CMS before publication — all rows in the dataset have valid Total Claims values
5. Data Year column added
Each file had no year column — the year was implicit in the filename. A Data Year column (2018, 2021, 2023) was added to each file before union to enable year-over-year analysis in Tableau.
6. Brand and Generic name standardization
Applied TRIM(UPPER()) calculated fields in Tableau to normalize case and whitespace inconsistencies across years — reducing apparent unique brand name count from ~7,000 to ~3,300 and generic names to ~2,000.
7. Phantom column removal
Excel introduced 16,363 empty trailing columns during editing (up to Excel's column maximum). These were stripped programmatically using Python before loading into Tableau, reducing file size from ~14MB to ~11MB per file.
________________________________________
Technical Notes
Union method: Three files unioned in Tableau Public using wildcard union (Year_*), producing a single 322,359-row dataset. Column name standardization in Excel was necessary for a clean union — mismatched names create null-filled duplicate columns.
Calculated fields created in Tableau:
Field	Formula
Brand Name (Clean)	TRIM(UPPER([Brand Name]))
Generic Name (Clean)	TRIM(UPPER([Generic Name]))
Claims per Beneficiary (Age 65+)	SUM([Age 65+ Claims]) / SUM([Age 65+ Beneficiaries])
Important caveats:
•	The dataset covers only Medicare Part D beneficiaries (elderly and some disabled Americans). It does not represent the broader US population or non-Medicare drug spending.
•	National-level rows were excluded from analysis. All national totals in the dashboard are aggregated from state-level rows.
________________________________________
Project Structure
medicare-partd-prescription-analysis/
│
├── data/
│   ├── Year_2018_clean.xlsx
│   ├── Year_2021_clean.xlsx
│   └── Year_2023_clean.xlsx
│
├── dashboard/
│   └── Medicare_Project.twbx
│
└── README.md
________________________________________
Skills Demonstrated
Data cleaning across multi-year schema mismatches · Column standardization · Geographic filtering · Suppression flag handling · Tableau union and extract · Choropleth mapping · Dual-axis combo charts · Stacked bar charts · Dashboard actions and interactivity · Calculated fields · Data storytelling
________________________________________
Connect
•	GitHub: sreeram123549
•	Tableau Public: sree.ram.bitla

