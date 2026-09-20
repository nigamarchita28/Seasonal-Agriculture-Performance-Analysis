# Seasonal Agriculture Performance Analysis

**VOIS AICTE Batch 1 (2026-2027) | Major Project | Data Visualization**

## Problem statement
Agricultural performance changes from one season to another because of differences in weather, farming practice, resource use and market conditions. Raw data does not show how performance changes. This project analyzes a dataset of 4,000 farms to find seasonal patterns, relationships and unusual observations, and turns them into data-driven recommendations.

## Dataset
`seasonal_agriculture_performance_dataset.csv`: 4,000 farms, 28 columns.

| Item | Details |
|---|---|
| Seasons | Kharif, Rabi, Zaid |
| Crops | Rice, Wheat, Maize, Cotton, Pulses, Groundnut, Chilli, Sugarcane |
| States | Andhra Pradesh, Gujarat, Karnataka, Madhya Pradesh, Maharashtra, Punjab, Tamil Nadu, Telangana |
| Variables | Weather and soil, fertilizer and pesticide use, irrigation method, yield, cost, revenue, profit, water use, disease and pest risk |

## Tools and libraries
Python | Pandas | NumPy | Matplotlib | Seaborn | SciPy | Jupyter Notebook / Google Colab

## What the notebook does
1. Loads and explores the dataset
2. Cleans the data (recovers missing yield from Production / Area, fills rainfall and soil moisture with seasonal medians, checks consistency and outliers)
3. Builds a crop-normalized **Yield Index** so different crops can be compared fairly
4. Compares seasons on yield, revenue, cost, profit, environment, resource use, water efficiency and disease risk
5. Studies correlations and checks whether patterns hold across irrigation methods and states
6. Tests differences with Kruskal-Wallis, Mann-Whitney U (Bonferroni corrected) and chi-square tests
7. Highlights unusual patterns and gives recommendations

## Key findings
* **Kharif > Rabi > Zaid** for yield in every crop and every state. Average profit falls from about ₹1.79 lakh (Kharif) to ₹0.88 lakh (Rabi) to -₹0.25 lakh (Zaid), and the share of loss-making farms rises from 42% to 51% to 64%.
* **Costs and inputs are the same in every season, but revenue is not**, which is why Zaid falls into losses.
* **Disease and pest risk follows wetness** (rainfall and humidity) and is highest in Kharif.
* **Crop choice matters as much as season:** Sugarcane and Chilli are profitable in all seasons, while Rice, Wheat and Maize lose money on average even in Kharif.
* **Drip irrigation is best in Kharif and Rabi, sprinkler in Zaid.** Flood irrigation uses the most water and loses money in Zaid.
* More fertilizer shows no link with higher yield or profit.
* All seasonal differences are statistically significant (p < 0.001), except inputs (fertilizer, pesticide, cost per hectare), which do not differ by season.

## How to run

**Google Colab (easiest)**
1. Open [colab.research.google.com](https://colab.research.google.com), then **File > Upload notebook** and choose `Seasonal_Agriculture_Performance_Analysis.ipynb`.
2. Run the first cells. When asked, upload `seasonal_agriculture_performance_dataset.csv`.
3. Choose **Runtime > Run all**.

**Locally**
1. Install Python, then run `pip install pandas numpy matplotlib seaborn scipy jupyter`.
2. Keep the notebook and CSV in the same folder, run `jupyter notebook`, and choose **Kernel > Restart & Run All**.

## Repository contents
* `Seasonal_Agriculture_Performance_Analysis.ipynb`: full analysis with charts and written insights
* `seasonal_agriculture_performance_dataset.csv`: dataset
* `README.md`: this file

## Limitations
* One observation per farm per season, so year-to-year trends cannot be studied.
* Correlation does not prove cause.
* District names do not match their states, so only state-level results are used.
* About 5.6% of yields sit at a 0.30 t/ha minimum, which suggests the data was capped.
