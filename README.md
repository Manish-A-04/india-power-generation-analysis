# India Power Generation Analysis (2023–2024)

An end-to-end data analysis project built in Microsoft Excel analyzing electricity generation trends, fuel source distribution, and regional grid performance across India.

---

## 📌 Project Overview

I built this project to analyze official monthly power generation data published by the **Central Electricity Authority (CEA), Ministry of Power, Government of India**. 

The dataset covers **305,429 MW of power capacity** across **542 operational power stations** in **37 Indian States and Union Territories** over a 7-month period (**July 2023 to January 2024**).

The objective was to take raw government CSV reports, clean and transform them in Excel, create dynamic Pivot Tables, and build a visual Executive Dashboard to evaluate grid performance against planned targets.

---

## 📑 Workbook Structure (4 Worksheets)

The Excel file ([`India_Power_Generation_Analytics_2023_2024.xlsx`](file:///c:/Users/hp/Desktop/project/India_Power_Generation_Analytics_2023_2024.xlsx)) is organized into 4 clear stages:

1. **`Raw Data`**: The source audit trail containing all 7 monthly CSV files stacked into a single table (**7,193 raw rows**).
2. **`Clean Data`**: The cleaned master table (**3,640 plant records**) with calculated columns for Target Variance, Target Fulfillment, YoY Growth, and Plant Efficiency (PLF %).
3. **`Pivot Analysis`**: Native Excel Pivot Tables summarizing electricity production by Month, by Fuel Source, and by Grid Region.
4. **`Dashboard`**: High-level visual dashboard featuring 4 KPI scorecards, a Target vs Actual Column Chart, a Fuel Mix Donut Chart, and a Regional Performance Summary Table.

---

## 🛠️ Step-by-Step: How I Analyzed the Data in Excel

### Step 1: Combining the Raw Files into Excel
* I used Excel's **Power Query / Get Data feature** (`Data ➔ Get Data ➔ From File ➔ From Folder`) to point to the folder containing the 7 monthly CEA reports.
* Clicking **`Combine & Transform Data`** stacked all 7 monthly files into a single unified table with **7,193 rows** in the **`Raw Data`** sheet.

![Combined Raw Data](raw_data_combined.png)

---

### Step 2: Cleaning the Data & Removing Subtotals
* The raw government tables contained subtotal and total summary rows mixed together with individual plant rows. If analyzed directly, this caused massive double-counting.
* Looking closely at the data, I noticed that **genuine power plant rows always had `NA` in Column H (`Stations`)**, while subtotal rows contained fuel types or state names.
* I applied an Excel filter on Column H, unchecked `(Select All)`, and selected **ONLY `NA`**. This eliminated all 3,553 summary rows in a single click, leaving **3,640 clean power plant records** in **`Clean Data`**.

![Cleaned Master Data](cleaned_data.png)

---

### Step 3: Adding Calculated Business Columns in Excel
In the `Clean Data` sheet, I added 4 formula columns:
1. **Variance (MU)**: `= L2 - K2` *(Actual Generation minus Planned Target)*
2. **Target Met %**: `= IFERROR(L2 / K2, 0)` *(Actual divided by Target, formatted as `0.0%`)*
3. **Year-over-Year Growth %**: `= IFERROR((L2 - M2) / M2, 0)` *(Actual minus Last Year Actual divided by Last Year)*
4. **Plant Efficiency % (PLF)**: `= IFERROR((L2 * 1000) / (J2 * D2 * 24), 0)` *(Actual MWh divided by Capacity in MW $\times$ Operating Hours)*

---

### Step 4: Building Native Pivot Tables for Analysis
In the **`Pivot Analysis`** sheet, I created 3 separate native Pivot Tables from `Clean Data`:
* **Monthly Summary Table**: Grouped by Month to compare planned target vs actual electricity generated each month.
* **Fuel Mix Table**: Grouped by `Fuel_Type` (Coal/Thermal, Hydro, Nuclear, Natural Gas) to analyze fuel contributions.
* **Regional Grid Table**: Grouped by `Region` to evaluate power production across the 5 electrical grid regions.

![Pivot Table Analysis](pivot_analysis.png)

---

### Step 5: Designing the Executive Dashboard
In the **`Dashboard`** sheet, I built:
* **4 KPI Scorecards**: Total Generation, Planned Target, Target Fulfillment Rate, and Clean Energy Share.
* **Monthly Clustered Column Chart**: Showing actual monthly output compared to targets.
* **Fuel Mix Doughnut Chart**: Highlighting the share of each fuel type in national electricity generation.
* **Regional Executive Summary Table**: A structured overview of regional output and percentage share.

![Executive Dashboard Overview](dashboard_1.png)

![Executive Dashboard Regional Grid Summary](dashboard_2.png)

---

## ⚡ Key Insights Based on the Current Analysis

### 1. National Power Generation Beat Planned Targets (+2.8% Surplus)
* Across the 7 months, India generated **883,451 Million Units (MU)** of electricity against a planned target of **859,484 MU**.
* This represents a **102.8% target fulfillment rate**, creating an overall national surplus of **+23,967 MU**.
* Peak power production occurred in **August 2023 (137,078 MU)** and **October 2023 (132,993 MU)** driven by post-monsoon industrial demand.

### 2. Coal / Thermal Remains the Overwhelming Grid Backbone (84.7% Share)
* **Coal and thermal plants generated 748,752 MU**, making up **84.7% of all electricity produced**.
* Thermal generation beat its planned target of 714,098 MU with a **104.9% target fulfillment rate**, acting as the essential baseload power supply.

### 3. Hydro Power Saw Shortfalls in Winter (86.4% Target Met)
* **Hydro plants generated 86,352 MU (9.8% national share)**, but fell short of the planned government target of 100,034 MU.
* Hydro generation peaked in August during peak monsoon inflow and dropped substantially during winter as dam reservoir water levels receded.

### 4. Nuclear & Gas Met Their Targets Reliably
* **Nuclear power plants produced 30,198 MU (3.4% share)**, beating their planned target of 27,453 MU by **+10.0% (110% target fulfillment)**.
* **Natural gas plants produced 18,149 MU (2.1% share)**, operating on-target with **101.4% target fulfillment**.

### 5. Western Grid is India's Primary Energy Powerhouse (37.5% Share)
* The **Western Region generated 331,575 MU (37.5% of national generation)**, beating its target of 296,604 MU by **+11.8%** and exporting power across inter-regional corridors.
* The **Northern Region was the second largest generator (218,246 MU, 24.7% share)**, followed by the **Southern Region (165,906 MU, 18.8% share)** and the **Eastern Region (154,429 MU, 17.5% share)**.

---

## 📁 Repository Contents

* **[`India_Power_Generation_Analytics_2023_2024.xlsx`](file:///c:/Users/hp/Desktop/project/India_Power_Generation_Analytics_2023_2024.xlsx)**: Complete 4-sheet Excel project (Raw Data, Clean Data, Pivot Analysis, Dashboard).
* **[`interview_walkthrough_guide.md`](file:///c:/Users/hp/Desktop/project/interview_walkthrough_guide.md)**: Plain-English interview walkthrough script.
* **[`data/`](file:///c:/Users/hp/Desktop/project/data)**: 7 monthly CEA power generation CSV reports (July 2023 to January 2024).
