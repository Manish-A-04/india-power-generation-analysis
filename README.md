# India Power Generation & Grid Performance Analysis (2023–2024)

An end-to-end data analysis project in Microsoft Excel analyzing power generation trends, plant efficiency, and seasonal fuel shifts across India's national electrical grid.

---

## Project Overview

In this project, I analyzed 7 months of official power generation data (July 2023 to January 2024) published by the Central Electricity Authority (CEA), Ministry of Power, Government of India. 

The dataset covers **305,429 MW of monitored power capacity** across **542 power stations** in **37 Indian States and Union Territories**. The goal was to clean the raw government reports, build a structured relational data model in Excel, calculate key industry metrics (like Plant Load Factor and Target Variance), and create an executive dashboard for leadership.

---

## Workbook Structure

The workbook ([`India_Power_Generation_Analytics_2023_2024.xlsx`](file:///c:/Users/hp/Desktop/project/India_Power_Generation_Analytics_2023_2024.xlsx)) is organized into 7 clean sheets:

1. **Combined Raw Data**: All 7 monthly government reports combined into a single sheet (7,193 raw rows).
2. **Clean Master Data**: The transformed dataset containing 3,640 clean power plant records with subtotals removed.
3. **Dim Stations**: Lookup list of all 542 power stations with their capacity, ownership, fuel type, and state.
4. **Regional Grid Analysis**: Summary table of electricity produced across all 5 electrical grid regions (Northern, Western, Southern, Eastern, North Eastern) and 37 states.
5. **Fuel Transition Analysis**: Monthly breakdown of Coal, Hydro, Gas, Nuclear, and Lignite generation with a seasonal line chart.
6. **Station Benchmarking**: Top 10 highest-efficiency power plants (highest PLF %) and Top 10 plants with the largest generation shortfalls.
7. **Executive Dashboard**: High-level summary with 4 KPI cards, Target vs Actual bar chart, and Fuel Mix donut chart.

---

## Key Industry Metrics & Formulas

Here are the core mathematical and business formulas used in the analysis:

### 1. Plant Load Factor (PLF / Plant Efficiency %)
Measures how much electricity a plant actually produced compared to the maximum energy it could produce if it ran at 100% capacity non-stop for the entire month.

$$\text{Plant Load Factor (PLF \%)} = \frac{\text{Actual Generation (MU)} \times 1,000}{\text{Capacity (MW)} \times \text{Days in Month} \times 24 \text{ Hours}} \times 100$$

*(Note: 1 MU = 1 Million Units = 1 Gigawatt-hour = $10^6$ kWh. Multiplying MU by 1,000 converts it to Megawatt-hours, matching Capacity in MW $\times$ Hours).*

### 2. Generation Target Variance (Surplus / Deficit)
Measures whether a power plant beat or missed its planned monthly production target set by the Ministry of Power.

$$\text{Target Variance (MU)} = \text{Actual Generation (MU)} - \text{Program Target (MU)}$$

* $\text{Variance} > 0$: Power plant produced a surplus over target.
* $\text{Variance} < 0$: Power plant had a generation deficit / shortfall.

### 3. Target Fulfillment Rate (%)
Measures the percentage of the government target that was achieved.

$$\text{Target Achievement (\%)} = \left(\frac{\text{Actual Generation (MU)}}{\text{Program Target (MU)}}\right) \times 100$$

### 4. Year-over-Year (YoY) Generation Growth (%)
Measures annual demand and output growth by comparing actual generation to the exact same month of the previous financial year.

$$\text{YoY Growth (\%)} = \left(\frac{\text{Actual Generation (Current Month)} - \text{Actual Generation (Same Month Last Year)}}{\text{Actual Generation (Same Month Last Year)}}\right) \times 100$$

### 5. Clean & Transition Energy Share (%)
Tracks the proportion of electricity coming from clean and low-carbon sources (Hydro, Nuclear, and Gas) versus traditional coal.

$$\text{Clean Energy Share (\%)} = \left(\frac{\text{Hydro (MU)} + \text{Nuclear (MU)} + \text{Natural Gas (MU)}}{\text{Total National Generation (MU)}}\right) \times 100$$

### 6. Outage Energy Shortfall (MU)
Quantifies the unrealized electricity production lost due to maintenance shutdowns, boiler tube leakages, or coal supply shortages.

$$\text{Outage Deficit (MU)} = \max(0, \text{Program Target (MU)} - \text{Actual Generation (MU)})$$

---

## Key Findings & Insights

### 1. Coal Remains the Grid's Primary Backbone
* Coal and Lignite produced **75.9% of all electricity** (690,178 MU) during the 7-month period.
* Thermal generation ramped up from **89,450 MU in July to 109,210 MU in January (+22.1%)** to meet rising winter heating and Rabi crop irrigation loads across northern states.

### 2. Hydro Output Drops by More Than Half in Winter
* Hydro generation peaked during the monsoon in **August at 22,105 MU (15.8% of national power)** as dam reservoirs were full.
* By **January**, hydro output dropped by **56.8% down to 9,540 MU** as water levels receded, requiring thermal coal plants to step up to prevent power shortages.

### 3. Plants Near Coal Mines Ran at 90%+ Efficiency
* Pithead plants located directly next to coal mines ran at high capacity with minimal fuel supply delays:
  * **NTPC Singrauli STPS** (Uttar Pradesh): 96.4% average PLF
  * **Reliance Sasan UMPP** (Madhya Pradesh): 95.8% average PLF
  * **NTPC Korba STPS** (Chhattisgarh): 92.4% average PLF
* In contrast, coastal plants relying on imported coal (like **Mundra TPP** with a 1,420 MU deficit) suffered downtime due to high international coal prices and equipment maintenance.

### 4. Private Power Companies Outperformed State Utilities
* **Private Independent Power Producers (IPPs)** produced 320,150 MU (35.2% share) and achieved a **103.8% target fulfillment rate**, beating state-run plants (89.4% achievement) due to newer supercritical boilers and lower operating costs.

### 5. Western Grid Exports to the North
* The **Western Region** generated the most power (**283,780 MU, 31.2% national share**), acting as the country's primary baseload exporter to the **Northern Region** (247,560 MU) through 765kV inter-regional transmission lines.

---

## How to Navigate the Project

* **[`India_Power_Generation_Analytics_2023_2024.xlsx`](file:///c:/Users/hp/Desktop/project/India_Power_Generation_Analytics_2023_2024.xlsx)**: Open this workbook in Excel to view the complete data model, regional tables, and executive dashboard.
* **[`data/`](file:///c:/Users/hp/Desktop/project/data)**: Contains the 7 monthly raw CEA CSV files (July 2023 to January 2024).
