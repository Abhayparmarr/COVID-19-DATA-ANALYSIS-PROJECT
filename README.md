# COVID-19 Global Data Analysis — Project 2

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Plots-4c72b0)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-F9AB00?logo=googlecolab&logoColor=white)

An end-to-end Exploratory Data Analysis (EDA) project examining global COVID-19 statistics across **225 countries and territories**. Built using **Python**, **Pandas**, **Matplotlib**, and **Seaborn**, this project covers data inspection, missing-value handling, statistical profiling, country-level rankings, continent-wise aggregations, and bivariate correlation analysis.

---

## Repository Structure

```text
COVID19-Data-Analysis/
│
├── COVID19_Data_Analysis_Project2_Executed.ipynb   # Pre-executed Jupyter / Google Colab notebook with all outputs & plots
├── covid19_analysis.py                             # Standalone Python script for local execution
├── COVID-19 Coronavirus.csv                        # Global COVID-19 dataset (225 rows × 10 columns)
├── charts/                                         # Generated high-resolution visualizations (PNG)
│   ├── 1_top5_cases.png
│   ├── 2_lowest5_cases.png
│   ├── 3_top5_deaths.png
│   ├── 4_top5_death_percentage.png
│   ├── 5_continent_cases.png
│   ├── 6_population_vs_cases.png
│   ├── 7_cases_vs_deaths.png
│   └── 8_spearman_heatmap.png
└── README.md                                       # Project documentation
```

---

## Key Analytical Insights

### 1. Global Scope & Data Cleaning
* **Dataset Coverage:** 225 countries and territories totaling **491.58 million confirmed cases** and **6.18 million deaths** (overall global fatality rate: **1.26%**).
* **Data Imputation:** Detected and resolved a single missing value in row index `135` (**Montenegro**, ISO code `MNE`) under the `Other names` column and standardized `ISO 3166-1 alpha-3 CODE` to `Iso_Code`.
* **Right-Skewed Distribution:** Mean cases per country (**2.18M**) are more than **13× higher** than median cases (**163,936**), showing that global totals are concentrated in a small number of large nations.

### 2. Country-Level Extremes
* **Top 5 Concentration:** The top five countries by total cases (**USA, India, Brazil, France, Germany**) account for **41.20%** of all global infections, while the top five by mortality (**USA, Brazil, India, Russia, Mexico**) account for **46.68%** of all global deaths.
* **Geographic Isolation:** Four of the five territories with the lowest case counts (**Micronesia, Saint Helena, Niue, Marshall Islands**) are isolated island territories.
* **Case Volume vs. Fatality Rate:** France and Germany recorded high case counts with low fatality percentages (`0.55%` and `0.60%`), whereas **Yemen (`18.15%`)**, **Sudan (`7.92%`)**, **Peru (`5.98%`)**, and **Mexico (`5.71%`)** experienced significantly higher case fatality rates.

### 3. Continent-Wise Breakdown
* **Europe (`180.33M` cases | `36.68%`)** and **Asia (`140.96M` cases | `28.67%`)** together account for **65.35%** of global cases.
* **Latin America & the Caribbean** recorded **13.73%** of global cases (`67.51M`) but accounted for **27.31%** of global deaths (`1.69M`).

### 4. Correlation Analysis (Spearman Rank)
* **Total Cases vs. Total Deaths ($r = 0.94$):** Strong positive correlation confirming that cumulative fatalities scale closely with total infections.
* **Population vs. Total Cases ($r = 0.69$):** Moderate-to-strong positive correlation with notable outliers across continents.
* **Cases per 1M vs. Death Percentage ($r = -0.46$):** Moderate negative correlation showing that countries with higher per-capita testing detected more mild cases, lowering their observed case fatality rate.

---

## How to Run This Project

### Option 1: Google Colab
1. Open [Google Colab](https://colab.research.google.com/) and upload `COVID19_Data_Analysis_Project2_Executed.ipynb`.
2. Upload `COVID-19 Coronavirus.csv` into the Colab **Files** sidebar.
3. Click **Runtime → Run all** to execute every cell and reproduce all tables and charts.

### Option 2: Local Python Environment (VS Code / Terminal)
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/COVID19-Data-Analysis.git
   cd COVID19-Data-Analysis
   ```
2. Install the required dependencies:
   ```bash
   pip install pandas matplotlib seaborn
   ```
3. Run the analysis script:
   ```bash
   python covid19_analysis.py
   ```
   All terminal summaries will print to the console, and all 8 visualizations will be exported to the `charts/` directory.