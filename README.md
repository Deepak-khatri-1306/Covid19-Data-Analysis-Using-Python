# Covid19-Data-Analysis-Using-Python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

# Display message indicating modules are imported
print('Modules are imported.')

# Load the dataset
df = pd.read_csv('covid19_Confirmed_dataset.csv')

# Display basic dataset information
print("Dataset Preview:")
print(df.head())
print(df.tail())
print("\nDataset Shape:", df.shape)
print("\nDataset Info:")
df.info()
print("\nStatistical Summary:")
print(df.describe())

# Remove the 'S.No' column (if it exists)
df = df.iloc[:, 1:]
print("\nUpdated Dataset Preview:")
print(df.head(2))

# Display dataset columns
print("\nDataset Columns:")
print(df.columns)

# Aggregate data by country
aggregating = df.groupby("Country/Region").sum()
print("\nAggregated Data Preview:")
print(aggregating.head())
print("\nAggregated Data Shape:", aggregating.shape)

# Visualizing COVID-19 cases for selected countries
plt.figure(figsize=(12, 6))
plt.plot(aggregating.loc["China"], label="China")
plt.plot(aggregating.loc["Italy"], label="Italy")
plt.plot(aggregating.loc["Spain"], label="Spain")
plt.xlabel("Days")
plt.ylabel("Number of Cases")
plt.title("COVID-19 Cases in China, Italy, and Spain")
plt.legend()
plt.show()

# Find the maximum infection rate for all countries
countries = list(aggregating.index)
max_infection_rates = [aggregating.loc[c].diff().max() for c in countries]
aggregating["Max Infection Rate"] = max_infection_rates

# Display the updated dataset
print("\nAggregated Data with Max Infection Rates:")
print(aggregating.head())

# Save the cleaned dataset for GitHub upload
aggregating.to_csv("covid19_analysis_results.csv")
print("\nProcessed data saved as 'covid19_analysis_results.csv'.")
