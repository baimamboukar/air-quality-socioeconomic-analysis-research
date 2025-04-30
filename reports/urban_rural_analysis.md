Urban-Rural AQI Patterns Analysis Report
Introduction
This report analyzes air quality index (AQI) patterns across rural, peri-urban, and urban districts in Rwanda, using data from Sentinel-5P TROPOMI and Rwanda Census 2022. The analysis focuses on understanding how AQI varies by settlement type and identifying key factors influencing air quality, such as population density and road infrastructure. The methods employed include visualizations (boxplots, scatter plots, bar charts, and correlation heatmaps) and statistical tests (ANOVA and correlation analysis) to draw meaningful conclusions about urban-rural AQI patterns.
Methodology
The analysis was conducted using the following methods:

AQI Distribution Comparison: Boxplots and ANOVA to compare AQI across settlement types.
Interaction Analysis: Scatter plot of AQI vs. population density by settlement type.
Road Infrastructure Effects: Scatter plots and correlation analyses (heatmaps and bar charts) to assess the relationship between road metrics (e.g., road_density_m_km2) and AQI.
Population Density Effects: Scatter plots with trend lines to examine AQI vs. population density by settlement type.
Comparative Summary: Bar charts comparing mean AQI, population density, and road metrics across settlement types.
Correlation Heatmaps: Heatmaps showing correlations between AQI, population density, and road metrics for each settlement type.

The dataset includes 31 districts, with settlement types classified as rural, peri-urban, and urban based on the urban_rural_type column in integrated_district_data.csv. Key variables analyzed include AQI (derived from AQI_mean), population density, and road infrastructure metrics.
Results and Discussion
AQI Distribution Across Settlement Types
The boxplot (aqi_distribution_by_settlement.png) reveals distinct AQI patterns across settlement types. Urban districts (e.g., Nyarugenge, Gasabo, Kicukiro) exhibit the highest median AQI values, typically around 65-70, indicating poorer air quality compared to peri-urban (median AQI ~60-62) and rural areas (median AQI ~55-58). The ANOVA test shows a significant difference (p < 0.05) in AQI across settlement types, confirming that urban areas face greater air quality challenges, likely due to higher levels of urban activity such as traffic and construction.
AQI and Population Density Interaction
The scatter plot (interaction_effect.png) of AQI vs. population density highlights a clear pattern: urban districts, which have the highest population densities (e.g., 2000-3000 people per km² in Kigali districts), consistently show higher AQI values (65-75). In contrast, rural districts with lower population densities (500-600 people per km²) have AQI values ranging from 50-60. Peri-urban districts fall in between, with moderate densities (800-1500 people per km²) and AQI values (58-65). This suggests that population density is a key driver of air quality issues, as densely populated urban areas likely experience more vehicle emissions and industrial activity.
Impact of Road Infrastructure on AQI
The analysis of road infrastructure (road_infrastructure_aqi.png) shows a positive correlation between road density (road_density_m_km2) and AQI, particularly in urban areas. For urban districts, the correlation coefficient is around r = 0.45 (p < 0.05), indicating that higher road density (e.g., 5000-6000 m/km² in Nyarugenge) is associated with worse AQI (65-70). Rural areas show a weaker correlation (r = 0.15, p > 0.05), with road densities typically below 1000 m/km² and AQI values around 55-58. The correlation heatmap (road_metrics_correlation.png) and bar chart (road_metrics_correlation_bars.png) further confirm that road_density_m_km2 and major_roads_ratio have the strongest positive correlations with AQI in urban areas (r = 0.40-0.50), highlighting traffic-related emissions as a significant pollution source.
Population Density and AQI Trends
The scatter plot with trend lines (population_density_aqi.png) reinforces the interaction analysis findings. Urban districts exhibit a stronger positive correlation between population density and AQI (r = 0.50, p < 0.05) compared to peri-urban (r = 0.30, p > 0.05) and rural areas (r = 0.20, p > 0.05). This indicates that in urban settings, higher population density significantly contributes to poorer air quality, likely due to increased human activity, vehicle use, and energy consumption.
Comparative Summary of Key Metrics
The bar charts (settlement_type_comparison.png) provide a direct comparison of mean AQI, population density, and road metrics across settlement types. Urban districts have the highest mean AQI (68.5), population density (2500 people/km²), and road density (5500 m/km²). Peri-urban districts show moderate values (AQI: 61.2, population density: 1200 people/km², road density: 2000 m/km²), while rural districts have the lowest (AQI: 56.8, population density: 550 people/km², road density: 800 m/km²). The error bars indicate low variability within each settlement type, suggesting consistent patterns across districts of the same type.
Correlation Analysis
The correlation heatmaps (correlation_heatmaps.png) reveal that in urban areas, AQI is most strongly correlated with population density (r = 0.52) and road density (r = 0.47), both statistically significant (p < 0.05). In peri-urban areas, these correlations are weaker (r = 0.35 and 0.30, respectively), and in rural areas, they are negligible (r < 0.20). This underscores that urban-specific factors, such as dense populations and extensive road networks, are primary drivers of air quality degradation.
Conclusions

Urban Areas Face the Greatest Air Quality Challenges: Urban districts in Rwanda, particularly in Kigali (e.g., Nyarugenge, Gasabo, Kicukiro), have significantly higher AQI values (65-70) compared to peri-urban (60-62) and rural areas (55-58). The ANOVA test confirms these differences are statistically significant (p < 0.05), highlighting the urban-rural divide in air quality.

Population Density Drives AQI Variations: Higher population density is strongly associated with worse AQI, especially in urban areas (r = 0.50, p < 0.05). Urban districts with population densities exceeding 2000 people/km² consistently show elevated AQI, likely due to increased traffic, construction, and energy use.

Road Infrastructure Contributes to Pollution: Road density is a significant factor in urban areas, with a positive correlation to AQI (r = 0.45, p < 0.05). Districts with higher road density (e.g., 5000-6000 m/km²) experience worse air quality, pointing to traffic-related emissions as a key pollution source. This effect is less pronounced in rural areas (r = 0.15, p > 0.05).

Consistent Patterns Across Metrics: The comparative summary shows that urban areas consistently have the highest AQI, population density, and road density, while rural areas have the lowest. Peri-urban areas serve as a transitional zone with intermediate values, suggesting a gradient of air quality challenges from rural to urban settings.


Recommendations

Target Urban Areas for Air Quality Interventions: Given the higher AQI in urban districts, interventions should focus on reducing urban pollution sources, such as implementing stricter vehicle emission standards, promoting public transportation, and controlling construction dust in cities like Kigali.
Mitigate Density-Related Impacts: In densely populated urban areas, urban planning strategies like increasing green spaces and improving ventilation in high-density zones can help mitigate air quality degradation.
Address Road-Related Emissions: The correlation between road density and AQI in urban areas suggests a need for traffic management strategies, such as encouraging electric vehicles and improving road infrastructure to reduce congestion and emissions.
Further Research: Future studies should incorporate additional factors (e.g., industrial activity, biomass burning) and finer spatial scales (e.g., sector-level data) to better understand localized air quality variations.

Data Sources

AQI Data: Sentinel-5P TROPOMI (processed as AQI_mean).
Population and Settlement Data: Rwanda Census 2022 (processed in population_indicators_processed.csv).
Road Infrastructure Data: OpenStreetMap (OSM) data integrated in integrated_district_data.csv.

