# COVID-19 Data Analysis
## Overview
This project analyzes COVID-19 confirmed cases data using Python. It includes data processing, aggregation, and visualization to understand infection trends across different countries.

## Data Processing
- Imported necessary libraries: `pandas`, `numpy`, `matplotlib.pyplot`, `seaborn`.
- Loaded the dataset from `covid19_Confirmed_dataset.csv`.
- Displayed basic dataset information: shape, info, and statistical summary.
- Removed the 'S.No' column to clean the dataset.
- Aggregated data by country for further analysis.

## Exploratory Data Analysis (EDA)
### Dataset Overview
- The dataset consists of COVID-19 confirmed cases by country and day.
- Aggregated country-level data to analyze trends.

### Visualization of COVID-19 Cases
- Plotted COVID-19 cases for **China, Italy, and Spain** to observe infection trends over time.
- **Visualizations:**
  - Line plot showing the number of cases over time for selected countries.

### Maximum Infection Rate Calculation
- Computed the **maximum daily infection rate** for each country by calculating the daily difference in cases.
- Added a new column `Max Infection Rate` to the aggregated dataset.

## Conclusion
- The project provides insights into COVID-19 trends, showing how cases evolved in different countries.
- **China, Italy, and Spain** were analyzed to observe peaks and infection growth patterns.
- Maximum infection rates help in understanding the severity of outbreaks in different regions.
