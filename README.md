# Manufacturing Downtime Analysis
___

## Executive Summary:

Downtime extended production time by 23 hours, **reducing line efficiency** by **36%**, with operator-related issues contributing **12% more to downtime than non-operator causes**. **Five factors** account for **80% of total downtime**, three (machine adjustment, batch change, batch coding) linked to operator errors. Mac’s downtime is mainly driven by **batch changes**, while other operators struggle more with **machine adjustments**. Average operator efficiency stands at 76%, with Mac slightly below the team average.

Recommended actions include **targeted operator training** supported by clear Standard Operating Procedures (SOPs), focused batch change coaching for Mac, machine adjustment training for other operators, strengthened **preventive maintenance**, and **real-time tracking** to maintain optimal stock levels.

## Business Problem:

For manufacturing companies, downtime directly impacts output and profitability through frequent production delays - such as machine breakdowns, power outages, inventory shortages, or operator mistakes -  without clear visibility into the main causes.

This analysis identifies key drivers of downtime and proposes actionable strategies to reduce operational disruptions.

## Methodology:

#### 1. Data Preparation
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

#### 2. Data Modelling
Designed a dimensional data model defining relationships with correct cardinality to ensure model integrity and enable factor-level, operator-level, and efficiency analysis.

| Primary Key                     | Foreign Key                           | Cardinality  |
|---------------------------------|---------------------------------------|--------------|
| Dim 'Downtime factors'[Factor]  | Fct 'Line downtime'[Downtime Factor]  | One-to-Many  |
| Fct 'Line downtime'[Batch]      | Fct 'Line productivity'[Batch]        | One-to-Many  |
| Dim 'Products'[Product_id]      | Fct 'Line productivity'[Product_id]   | One-to-Many  |

#### 3. KPI Development (DAX)
Defined key operational metrics to quantify downtime impact.

| SN | KPI                        | Logic/Definition                                              | Remarks                                            |
|----|----------------------------|---------------------------------------------------------------|----------------------------------------------------|
| 1  | Overall Line Efficiency    | (Planned Batch Time) / (Actual Batch Time)                    | Measures adherence to planned production time      |
| 2  | Operators Efficiency       | Overall Line Efficiency filtered to operator-related causes   | Isolates operator impact only                      |
| 3  | Total Downtime Minutes     | SUM(Downtime Minutes)                                         | Actual Batch Minutes - Planned Batch Mainutes      |
| 4  | Pareto Distribution        | Cumulative % of SUM(Downtime Minutes) by ranked cause         | Highlights major downtime drivers (80% impact)     |

#### 4. Exploratory Analysis
Conducted exploratory and root-cause analysis to isolate high-impact downtime drivers and operator-specific patterns.

#### 5. Data Visualisation & Insight Communication
Developed a Power BI report using data storytelling principles, with descriptive narration and highlighted insights, visualising top downtime drivers, operator-specific issues, and factor-level impacts to clearly communicate operational risks and prioritised actions.

## Insights & Recommendations:

<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/manufacturing downtime report.jpg" width="1000">

___

#### Miscellaneous:

##### 1.1 `Line downtime table` transformation

- **raw production log** (`Line downtime table`)
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/Line downtime table_raw.png" width="500">

- `Line downtime table` **after unpivoting**
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/Line downtime table_unpivoted.png" width="500">

##### 1.2 [Data set](https://mavenanalytics.io/data-playground/manufacturing-downtime)
