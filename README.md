# Manufacturing Downtime Analysis
___

## Executive Summary:

Production downtime **reduced line efficiency** by **36%**, with operator-related issues contributing **12% more downtime than non-operator causes**. **Five factors** account for **80% of total downtime**, three (machine adjustment, batch change, batch coding) linked to operator errors. Mac’s downtime is mainly driven by **batch changes**, while other operators struggle more with **machine adjustments**. Average operator efficiency stands at 76%, with Mac slightly below the team average.

Recommended actions include **targeted operator training** supported by clear SOPs, focused batch change coaching for Mac, machine adjustment training for other operators, strengthened **preventive maintenance**, and **real-time tracking** to maintain optimal stock levels.

## Business Problem:

For manufacturing companies, downtime directly impacts output and profitability through frequent production delays without clear visibility into the main causes.

This analysis identifies key drivers of downtime and proposes actionable strategies to reduce operational disruptions.

## Methodology:

#### 1. Data Preparation
Imported four Excel tables, cleaned and transformed data in Power Query.

#### 2. Data Modelling
Designed relationships, structured fact/dimension logic, and validated model integrity.

#### 3. KPI Development (DAX)
Built explicit measures and applied context-driven calculations.

#### 4. Exploratory Analysis
Analysed trends, segments, and drivers across key dimensions.
OR
Explored trends, segments, and performance drivers to answer business questions.

1. Extracted and transformed production downtime records using Power Query, ensuring data quality and standardised categorisation.
2. Designed a structured data model in Power BI to enable factor-level, operator-level, and efficiency analysis.
3. Defined key operational metrics (downtime minutes, downtime %, operator efficiency, Pareto distribution) to quantify impact.
4. Conducted exploratory and root-cause analysis to isolate high-impact downtime drivers and operator-specific patterns.
5. Developed a structured Power BI report using data storytelling principles, with descriptive narration and highlighted insights to clearly communicate operational risks and priorities.

#### Checks
1. Extracted and cleaned downtime records from the production line excel file using Power Query.
2. Replaced "No" with *Non-Operator* and "Yes" with *Operator* in the "Operator Error" column of the "Downtime factors" table to ease reading the "Legend" in visuals.
3. Modelled data and performed detailed exploratory analysis using Power BI to quantify downtime distribution and identify critical drivers.
4. Visualized downtime data in Power BI to compare downtime contribution by operators, machine failure, and inventory shortages.

## Insights & Recommendations:

<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/manufacturing downtime report.jpg" width="1000">

___

#### Miscellaneous:

##### 1.1 `Line downtime table` transformation

- **raw** `Line downtime table`
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/Line downtime table_raw.png" width="500">

- `Line downtime table` **after unpivoting**
<img src="https://raw.githubusercontent.com/jakejosh6751/Manufacturing-Downtime-Analysis-/main/Line downtime table_unpivoted.png" width="500">

[Data set](https://mavenanalytics.io/data-playground/manufacturing-downtime)
