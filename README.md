# Manufacturing Downtime Analysis
___

## Project Objective:

For manufacturing companies, **downtime** directly **impacts output and profitability** through **frequent production delays** resulting from;
- Machine breakdowns
- Power outages
- Inventory shortages
- Operator mistakes

These challenges occur without clear visibility into the main causes.

This analysis identifies **key drivers of downtime** and proposes actionable **strategies to reduce operational disruptions**.

## Key Findings:

- Overall Line Efficiency: **64%**
- Production Time Extension: **+23 hours**
- Operator vs Non-Operator Downtime: **Operator +12% higher**
- Top Downtime Causes: Top 5 factors = **80%**; Machine adjustment, Machine failure, Inventory shortage, Batch change, Batch coding error
- Operator Error Drivers: **Machine adjustment, Batch change, Batch coding error**
- Avg Operator only Efficiency: **76%**

### Key Findings Visualised with Recommendations:

<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/manufacturing downtime report.jpg" width="1000">

## Methodology:

### 1. Data Preparation
Imported four tables from Excel and transformed the data in Power Query - renamed columns, unpivoted production log (Line downtime table), and standardised data types. Key table attributes are summarised here:

- **Downtime factors** - Dimension table with details on each downtime factor with attributes;
  - `Factor` - Unique identifier for each downtime factor (PK)
  - `Description` - Including "Emergency stop", "Batch change", "Batch coding error", etc.
  - `Operator Error` - Boolean flag indicating if `Description` is an operator error (Yes/No).
- **Line downtime** - Fact table containing downtime (in minutes) by factor for each batch
  - `Batch` - Unique identifier for each batch (PK)
  - `Downtime Factor` - Points to `Factor` in **Downtime factors** (FK)
  - `Downtime Minutes` - Downtime duration in minutes (Integer)
- **Line productivity** - Fact table containing details for each batch produced - Date, Product_id, Batch, Operator, Start Time, End Time
- **Products** - Dimension table with details on each product - Product_id, Flavor, Size, Min batch time

### 2. Data Modelling
Designed a dimensional data model defining relationships with correct cardinality to ensure model integrity and enable factor-level, operator-level, and efficiency analysis.

| Primary Key                     | Foreign Key                           | Cardinality  |
|---------------------------------|---------------------------------------|--------------|
| Dim 'Downtime factors'[Factor]  | Fct 'Line downtime'[Downtime Factor]  | One-to-Many  |
| Fct 'Line downtime'[Batch]      | Fct 'Line productivity'[Batch]        | One-to-Many  |
| Dim 'Products'[Product_id]      | Fct 'Line productivity'[Product_id]   | One-to-Many  |

### 3. KPI Development (DAX)
Defined key operational metrics to quantify downtime impact.

| SN | KPI                        | Logic/Definition                                              | Remark                                             |
|----|----------------------------|---------------------------------------------------------------|----------------------------------------------------|
| 1  | Overall Line Efficiency    | (Planned Batch Time) / (Actual Batch Time)                    | Measures adherence to planned production time      |
| 2  | Operators Efficiency       | Overall Line Efficiency filtered to operator-related causes   | Isolates operator impact only                      |
| 3  | Total Downtime Minutes     | SUM(Downtime Minutes)                                         | Actual Batch Minutes - Planned Batch Mainutes      |
| 4  | Pareto Distribution        | Cumulative % of SUM(Downtime Minutes) by ranked cause         | Highlights major downtime drivers (80% impact)     |

### 4. Exploratory Analysis
Conducted exploratory and root-cause analysis to isolate high-impact downtime drivers and operator-specific patterns.

### 5. Data Visualisation & Insight Communication
Developed a Power BI report using data storytelling principles, with descriptive narration and highlighted insights, visualising top downtime drivers, operator-specific issues, and factor-level impacts to clearly communicate operational risks and prioritised actions.
___

## Author

**Jacob Joshua**

Data Analyst

- [GitHub](https://github.com/jacobdbt2100/Data-Analytics-Projects/blob/main/README.md)
- [LinkedIn](https://www.linkedin.com/in/jacobjoshua675/)
___

#### Miscellaneous:

##### M.1 `Line downtime table` transformation

- **raw production log** (`Line downtime table`)
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/Line downtime table_raw.png" width="500">

- `Line downtime table` **after unpivoting**
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/Line downtime table_unpivoted.png" width="500">

##### M.2 [Data set](https://mavenanalytics.io/data-playground/manufacturing-downtime)

### Author

**Jacob Joshua**

jacobjoshua675@gmail.com

- [X(Twitter)](https://x.com/jacobdbt2100_2)
- [LinkedIn](https://www.linkedin.com/in/jacobjoshua675/)
- [GitHub](https://github.com/jacobdbt2100/Data-Analytics-Projects/blob/main/README.md)
