# Correlation Analysis of Air Quality and Socioeconomic Factors in Rwanda

## Abstract

This report presents the results of a correlation analysis examining the relationship between air quality and various socioeconomic and geographic factors across Rwandan districts. The analysis was conducted to address the question posed in our earlier exploratory data analysis: does air pollution exposure vary by socioeconomic status in Rwanda, and are vulnerable communities more affected? Our findings reveal moderate correlations between air quality and urbanization metrics, with weaker associations to road infrastructure factors, suggesting a more complex relationship than the traditional environmental justice narrative.

## 1. Introduction

Our initial analysis found only a weak correlation between poverty and air quality in Rwanda, prompting this more comprehensive investigation that incorporates additional variables as suggested by our professor. This correlation analysis expands our understanding by examining relationships between Air Quality Index (AQI) and multiple socioeconomic and geographic factors, including:

- Urban/rural classification
- Population density
- Road infrastructure metrics
- Year-over-year air quality changes

By quantifying these relationships, we aim to better understand the complex dynamics of air pollution distribution in Rwanda and identify the strongest predictors of air quality.

## 2. Methodology

We conducted both Pearson and Spearman correlation analyses to examine linear and monotonic relationships, respectively. This dual approach accounts for potentially non-linear relationships between variables.

### 2.1 Correlation Coefficients

Pearson's correlation coefficient measures the linear relationship between two variables and is calculated as:

$$r = \frac{\sum_{i=1}^{n} (x_i - \bar{x})(y_i - \bar{y})}{\sqrt{\sum_{i=1}^{n} (x_i - \bar{x})^2 \sum_{i=1}^{n} (y_i - \bar{y})^2}}$$

Spearman's rank correlation assesses monotonic relationships by ranking the data and is more robust to outliers:

$$\rho = 1 - \frac{6 \sum d_i^2}{n(n^2 - 1)}$$

Where $d_i$ is the difference between ranks of corresponding variables.

### 2.2 Variables Analyzed

The analysis included 7 key variables:
- Urban percentage
- Rural percentage
- Population density
- Road density
- Proximity to major roads (Within 1km)
- Average year-over-year change in AQI
- Road coverage metrics

### 2.3 District Classification

Districts were classified into three categories based on urban percentage:
- Rural: urban percentage < 15%
- Peri-urban: 15% ≤ urban percentage < 50%
- Urban: urban percentage ≥ 50%

### 2.4 Software Implementation

The analysis was implemented in Python using pandas for data manipulation, scipy.stats for statistical calculations, matplotlib and seaborn for visualization, with a custom-built `CorrelationAnalysis` class to ensure consistent methodology.

## 3. Results

### 3.1 Overall Correlations with AQI

#### Pearson Correlation Coefficients:
- Urban Percentage: 0.516
- Rural Percentage: -0.516
- Population Density: 0.489
- Road Density: 0.254
- AVG YoY Change: 0.174
- Within 1km of major roads: 0.107

#### Spearman Correlation Coefficients:
- Urban Percentage: 0.400
- Rural Percentage: -0.400
- Population Density: 0.307
- AVG YoY Change: 0.291
- Road Density: 0.093
- Within 1km of major roads: -0.084

### 3.2 Key Findings

1. **Urbanization metrics** showed the strongest correlation with AQI, with urban percentage having a moderate positive correlation (r = 0.516) and rural percentage having an equal but negative correlation.

2. **Population density** showed the second strongest correlation (r = 0.489), reinforcing the importance of human settlement patterns in air quality outcomes.

3. **Road infrastructure metrics** showed weaker correlations than urbanization variables, with road density having a weak positive correlation (r = 0.254).

4. **Year-over-year changes** in AQI showed a weak positive correlation (r = 0.174), suggesting that areas with higher pollution may be experiencing greater increases in pollution over time.

5. **Differences between Pearson and Spearman** correlations suggest some non-linear relationships, particularly for road-related metrics where Spearman coefficients were notably different.

## 4. Discussion

### 4.1 Urbanization and Air Quality

The moderate positive correlation between urban percentage and AQI indicates that more urbanized districts generally experience higher air pollution levels. This is consistent with the concentration of emission sources in urban areas, including vehicles, industrial activities, and higher population density. The perfectly opposite correlation for rural percentage (-0.516) is mathematically expected since urban and rural percentages are complementary.

### 4.2 Population Density as a Key Factor

The relatively strong correlation between population density and AQI (r = 0.489) suggests that human concentration plays a significant role in air pollution patterns, even when controlling for other factors. This could be attributed to increased energy consumption, transportation needs, and other anthropogenic activities associated with higher population densities.

### 4.3 Road Infrastructure and Air Quality

The weaker correlations between road infrastructure metrics and AQI indicate a more complex relationship than expected. While road density shows a positive correlation (r = 0.254), suggesting some association between transportation infrastructure and pollution, the effect is not as strong as urbanization factors. This could be due to:

1. The relatively sparse road network in many parts of Rwanda
2. Varying vehicle numbers and types on different roads
3. Other factors like industrial emissions or geographical features having stronger influences

### 4.4 Environmental Justice Implications

The relatively modest correlations between socioeconomic indicators and AQI challenge the traditional environmental justice narrative often observed in other countries. In Rwanda, the relationship appears to be driven more by urbanization patterns than by socioeconomic status alone. This suggests that air quality management strategies may need to focus primarily on urban planning and transportation policies rather than targeting interventions based solely on economic indicators.

## 5. Conclusion

This correlation analysis reveals that air quality in Rwanda is most strongly associated with urbanization metrics and population density, with weaker correlations to road infrastructure variables. These findings suggest that the relationship between air quality and socioeconomic factors in Rwanda follows a pattern different from the traditional environmental justice narrative observed in many industrialized countries.

The moderate strength of the correlations (r ≤ 0.516) indicates that air quality is influenced by multiple factors beyond those analyzed here, possibly including industrial activity, geographical features, and meteorological conditions. This complexity underscores the need for multifaceted approaches to air quality management that consider the unique developmental context of Rwanda.

Future research should investigate temporal trends in air quality by socioeconomic status and explore potential interaction effects between urbanization, transportation, and industrial development. Additionally, more granular sector-level analysis may reveal localized patterns that are obscured at the district level.

*Data Sources: Sentinel-5P TROPOMI satellite data (2020-2025), Rwanda Census 2022, OSM Road Network*