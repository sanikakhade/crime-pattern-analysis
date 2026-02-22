# 🔍 Ireland Crime Pattern Analysis

A data-driven analysis of recorded crime incidents across Ireland using the official [CJA07 dataset from data.gov.ie](https://data.gov.ie). This project uncovers temporal trends, geographical hotspots, and offence-type distributions using Python-based data processing and visualization pipelines.

> 📚 Academic Project — Programming for AI Module | MSc in Artificial Intelligence | National College of Ireland (2025)

---

## 📌 Project Overview

This project programmatically ingests, cleans, transforms, and visualizes Ireland's recorded crime data to answer key questions:

- How have crime rates in Ireland changed over the years?
- Which Garda stations and divisions report the highest crime volumes?
- What are the most frequently occurring offence types?
- Are there identifiable upward or downward trends in specific crime categories?

---

## 🗂️ Dataset

| Detail | Info |
|---|---|
| **Source** | [data.gov.ie — CJA07 Recorded Crime Incidents](https://data.gov.ie) |
| **Format** | CSV (Structured) |
| **Records** | 1,000+ entries |
| **Key Attributes** | Year, Garda Station, Garda Division, Type of Offence, Crime Count |

---

## 🛠️ Tech Stack

| Tool / Library | Purpose |
|---|---|
| **Python** | Core programming language |
| **Pandas** | Data manipulation & aggregation |
| **NumPy** | Numerical operations |
| **Matplotlib** | Line charts, bar charts, pie charts |
| **Seaborn** | Heatmaps & styled visualizations |
| **Scikit-learn** | Feature analysis & clustering |
| **SQLite3** | Storing raw and processed datasets |
| **Jupyter Notebook** | Interactive analysis & documentation |

---

## ⚙️ Data Pipeline

```
Raw CSV ──► SQLite (crime_raw) ──► Preprocessing ──► Feature Engineering ──► EDA & Analysis ──► Visualizations ──► Transformed CSVs
```

### Stage 1 — Data Ingestion
- Load CSV using Pandas
- Store raw data into SQLite database (`crime.db`) as `crime_raw` table

### Stage 2 — Preprocessing
- Rename and standardise column names
- Clean Garda station names (remove leading numeric codes)
- Standardise offence category names (remove trailing codes)
- Extract Garda Division from station name
- Handle null values and remove duplicate rows
- Convert data types (numeric coercion for codes and values)

### Stage 3 — Transformation & Feature Engineering
- Aggregate total crimes per year
- Aggregate total crimes per Garda station
- Aggregate total crimes per offence type
- Aggregate total crimes per Garda division
- Compute Year-over-Year (YoY) percentage change in crime totals
- Extract crime trends per offence type across years

### Stage 4 — Analysis
- Identify highest and lowest crime years
- Find the year with the highest YoY increase
- Rank top 10 Garda stations by total crime
- Determine the most common offence category
- Detect offence types with long-term increasing trends

### Stage 5 — Visualization
- Line chart — yearly crime trend
- Bar charts — crimes by offence type and top Garda stations
- Heatmap — offence trends across years
- Pie chart — distribution of crime categories

---

## 📊 Visualizations

| Chart Type | Insight |
|---|---|
| 📈 Line Chart | Total crime trend in Ireland year-over-year |
| 📊 Horizontal Bar Chart | Total crimes ranked by offence type |
| 📊 Horizontal Bar Chart | Top 10 Garda stations by total crime volume |
| 🌡️ Heatmap | Offence type trends across all years |
| 🥧 Pie Chart | Proportional distribution of crime by offence category |

---

## 📁 Project Structure

```
ireland-crime-analysis/
│
├── CJA07_Recorded_crime_incidents.ipynb   # Main analysis notebook
├── CJA07.20251212152238.csv               # Raw dataset (download from data.gov.ie)
└── README.md
```

---

## 🚀 How to Run

### Prerequisites
Make sure you have Python 3.8+ installed.

### Step 1 — Clone the repository
```bash
git clone https://github.com/sanikakhade/crime-pattern-analysis.git
cd crime-pattern-analysis
```

### Step 2 — Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Step 3 — Download the dataset
Visit [data.gov.ie](https://data.gov.ie) and search for **CJA07 Recorded Crime Incidents**.
Download the CSV and place it in the project root directory.

### Step 4 — Launch the notebook
```bash
jupyter notebook CJA07_Recorded_crime_incidents.ipynb
```

### Step 5 — Run all cells
Run the notebook cells in order:
1. **Ingestion** — Loads data and creates SQLite DB
2. **Preprocessing** — Cleans and standardises the data
3. **Transformation** — Generates aggregated CSV files
4. **Analysis** — Prints key findings to console
5. **Visualization** — Displays all charts

---

## 🔑 Key Findings

- 📅 Identified the **peak and lowest crime years** in Ireland from the dataset
- 🏢 Mapped the **top 10 highest-crime Garda stations** across the country
- 🔺 Uncovered **long-term upward trends** in specific offence categories
- 🗺️ Revealed **geographic distribution patterns** of crime across Garda divisions

---

## 🔮 Future Work

- Integrate socio-economic indicators for multi-dataset correlation analysis
- Implement ML models (ARIMA, Random Forest) for crime forecasting at neighbourhood level
- Build an interactive real-time dashboard using Plotly / Dash
- Expand analysis with CCTV locations and demographic data

---

## 👥 Team

Group project — MSc in Artificial Intelligence, National College of Ireland (2025)
Module: Programming for AI
---

## 📜 License

This project is for academic purposes only. Dataset sourced from [data.gov.ie](https://data.gov.ie) under the Open Government Licence.
