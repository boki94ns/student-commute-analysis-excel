# Student Commute Analysis | Exploratory Data Analysis in Excel

**Excel portfolio project — descriptive statistics, probability distributions, and correlation analysis**

## Project overview

This project explores commuting patterns in a dataset of **500 students**. The analysis examines commuting time, travel distance, transport mode, transport costs, transfers, delays, and the number of commuting days per week.

The goal is to practice exploratory data analysis (EDA) in Microsoft Excel, summarize travel-time variability, investigate possible outliers, and assess relationships between numerical variables.

## Dataset

The `Podaci` worksheet includes **500 student records** with these populated fields:

| Column | Description |
|---|---|
| `Student_ID` | Unique student identifier |
| `Vreme_putovanja_min` | Commute duration in minutes |
| `Udaljenost_km` | Travel distance in kilometers |
| `Broj_presedanja` | Number of transfers |
| `Nacin_prevoza` | Transport mode |
| `Cena_putovanja_RSD` | Travel cost in Serbian dinars |
| `Kasnjenje_min` | Delay in minutes |
| `Broj_dana_nedeljno` | Commuting days per week |

The source also contains a `Z_score` header, but its cells are **not populated** in the supplied workbook, so z-score calculations are not listed among the completed analyses.

### Transport modes

| Mode | Students |
|---|---:|
| Bicycle (`Bicikl`) | 123 |
| Walking (`Peške`) | 99 |
| Car (`Automobil`) | 97 |
| Tram (`Tramvaj`) | 92 |
| Bus (`Autobus`) | 89 |
| **Total** | **500** |

## Tools and methods

**Tool:** Microsoft Excel

- **Descriptive statistics:** `COUNT`, `MIN`, `MAX`, `AVERAGE`, `MEDIAN`, `STDEV.S`, `VAR.S`, `SKEW`
- **Distribution and percentiles:** `QUARTILE.INC`, `PERCENTILE.INC`, `NORM.DIST`
- **Outlier screening:** interquartile range (IQR), lower/upper fences based on `1.5 × IQR`
- **Relationships between variables:** `CORREL` (Pearson correlation coefficient)
- **Visualizations:** line charts for normal-distribution calculations and scatter plots for numerical relationships

## Workbook structure

| Worksheet | What it contains |
|---|---|
| `Podaci` | Source data for 500 students |
| `EDA` | Descriptive statistics for commute times, percentiles, IQR, and outlier thresholds |
| `GrafikoniNormalna` | `NORM.DIST` calculations and distribution charts |
| `Korelacija` | Three Pearson correlation coefficients computed with `CORREL` |
| `Scatter` | Three scatter charts showing relationships between numeric variables |
| `BoxPlots` | Data columns organized for box-plot exploration; no separate box-plot chart is included in this workbook |

## Key results

### 1. Travel-time descriptive statistics

The values below come from the calculations in the `EDA` worksheet.

| Metric | Result |
|---|---:|
| Number of students | 500 |
| Minimum travel time | 5 min |
| Maximum travel time | 72 min |
| Mean travel time | 36.27 min |
| Median travel time | 36 min |
| Standard deviation | 13.42 min |
| Variance | 180.15 min² |
| Skewness | 0.028 |
| First quartile (Q1) | 27 min |
| Third quartile (Q3) | 47 min |
| 90th percentile | 53.10 min |
| 95th percentile | 57 min |
| Interquartile range (IQR) | 20 min |
| Lower outlier fence | −3 min |
| Upper outlier fence | 77 min |

**Interpretation:** Typical travel time is around 36 minutes. The calculated lower and upper IQR fences are −3 and 77 minutes; because the observed values range from 5 to 72 minutes, this rule identifies **no commute-time outliers** in the dataset.

### 2. Correlation analysis

| Variables | Pearson r | Interpretation |
|---|---:|---|
| Travel distance vs. commute time | **0.854** | Strong positive association |
| Travel cost vs. distance | **0.026** | Very weak linear association |
| Commute time vs. delay | **−0.037** | Very weak negative linear association |

The clearest relationship is between **distance and travel time**: longer distances generally correspond to longer commutes. These correlations show associations, **not causation**.

### 3. Normal-distribution exploration

The `GrafikoniNormalna` worksheet uses `NORM.DIST` with the travel-time mean and standard deviation from `EDA`, including probability density and cumulative distribution values. The workbook includes two distribution line charts. This is **distribution analysis**, not a trained predictive or machine-learning model.

### 4. Additional descriptive context

Across all 500 records, average travel distance is approximately **12.04 km**, average listed travel cost is **192.12 RSD**, and average delay is **2.13 minutes**. Travel costs include zero-valued journeys, such as walking and cycling.

## Key takeaways

1. Commute times vary from **5 to 72 minutes**, with a mean of **36.27 minutes**.
2. Distance has a **strong positive correlation** with travel time (`r ≈ 0.854`).
3. The analyzed data shows **almost no linear relationship** between distance and listed travel cost or between travel time and delay.
4. Using statistical functions, percentiles, IQR and charts provides a structured workflow for exploring transport-related data in Excel.

## Files

- **[Student_Commute_Analysis.xlsx](Student_Commute_Analysis.xlsx)** — original project workbook, with six worksheets and Excel charts.
- **`README.md`** — project documentation, analysis workflow and verified results.

## Project context

An educational Excel / data analytics portfolio project. Results describe the supplied dataset; they should not be generalized to all students without additional information about how the data was collected.
