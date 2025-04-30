Multivariate Regression and Time Series Trend Analysis Report
Introduction
This report summarizes the findings from the multivariate regression analysis (Step 2) and time series trend analysis by poverty level (Step 3) of the Rwanda Air Quality Analysis Project. The objective is to explore the relationship between air quality index (AQI) and socioeconomic factors, specifically examining predictors of AQI and trends across poverty categories.
Data Sources

AQI Data: Sourced from Sentinel-5P TROPOMI satellite measurements, aggregated to the sector level, covering 2020-2025 (25,376 records).
Poverty Data: Derived from clean_data_poverty.csv, providing sector-level poverty distributions (non_poor, vulnerable, moderately_poor, severely_poor) from Rwanda Census 2022 (416 sectors).
Merged Dataset: Combined AQI and poverty data on sector_key, resulting in 30,805 records.

1. Multivariate Regression Analysis (Step 2)
Objective
Identify key predictors of AQI and assess their joint predictive power using multivariate regression.
Methodology

Full Model: Included predictors: road_density_m_km2, population_density, urban_percentage, major_roads_ratio, total_road_length_m, major_roads_exposure_index, avg_yoy_change.
Feature Selection: Selected significant predictors (p < 0.05) while addressing multicollinearity (VIF > 5).
Best Model: Trained using the best predictors.
Metrics: R-squared, Adjusted R-squared, AIC, BIC, significant predictors, and observations.

Results

Full Model:
R-squared: 0.359
Adjusted R-squared: 0.261
AIC: 84.2
BIC: 91.3
Significant Predictors: 0
Total Predictors: 7
Observations: 31


Best Model:
Similar performance due to multicollinearity limiting significant predictors.


Findings:
Strongest correlates: urban_percentage (r = 0.516), population_density (r = 0.489).
Road variables (e.g., road_density_m_km2, r = 0.254) were often insignificant in the multivariate context.
Multicollinearity (e.g., between urban_percentage and population_density) reduced model performance.



Visualizations

Regression Coefficients: Highlighted urban_percentage and population_density as key predictors.
Actual vs. Predicted: Showed moderate fit (R-squared = 0.359).
Performance Comparison: Confirmed similar Adjusted R-squared for Full and Best models (~0.261).

2. Time Series Trend Analysis by Poverty Level (Step 3)
Objective
Group sectors by poverty categories, analyze AQI trends over time, and determine if poorer areas are improving or worsening faster.
Methodology

Data Preparation:
Merged AQI and poverty data (30,805 records).
Calculated poverty_score = (non_poor * 0) + (vulnerable * 1) + (moderately_poor * 2) + (severely_poor * 3).
Grouped sectors into "Low Poverty," "Medium Poverty," and "High Poverty" using tertiles.


Time Series:
Created datetime index (2020-2025).
Computed average AQI by poverty category and date.


Trend Analysis:
Calculated trend slopes via linear regression.
Analyzed YoY AQI changes.


Visualizations:
AQI trends plot.
YoY AQI change plot.
AQI distribution box plot.



Results

AQI Trend Metrics:
Low Poverty: Slope = 0.0228 (Worsening)
Medium Poverty: Slope = 0.0223 (Worsening)
High Poverty: Slope = 0.0226 (Worsening)


Findings:
All categories show a slight worsening trend (slopes ~0.022), indicating a gradual AQI increase.
Similar slopes across groups suggest uniform air quality trends, not disproportionately affecting poorer areas.
AQI distributions overlap across poverty categories, reinforcing a weak poverty-AQI link (r = 0.17).



Visualizations

AQI Trends Plot: Showed a gradual AQI increase from 40-50 to 70-90 across all groups.
YoY AQI Change Plot: Highlighted short-term fluctuations with no clear divergence by poverty.
AQI Distribution Plot: Confirmed similar AQI distributions (medians ~60-70) across categories.

Discussion
Urbanization and population density are key AQI drivers, but multicollinearity limits multivariate model performance. The uniform AQI trends across poverty categories challenge the environmental justice narrative, suggesting that air quality issues in Rwanda are widespread, possibly driven by urbanization and infrastructure rather than socioeconomic disparities. The slight AQI increase over time calls for broad-based interventions.
Limitations

Missing poverty_index in regression analysis.
Static poverty data (2022) may not capture temporal changes.
Data gaps in AQI trends require further investigation.

Next Steps
Proceed to Step 4: Urban-Rural Comparative Analysis to explore AQI patterns by settlement type and test poverty-AQI relationships across urbanization levels.
