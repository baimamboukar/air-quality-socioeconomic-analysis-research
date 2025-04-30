# Data Processing Methodology Report

## Introduction

Following the professor's feedback on our initial analysis of socioeconomic air quality disparities in Rwanda, we expanded our data processing to incorporate additional variables, urban-rural distinctions, road network features, and temporal trend analysis. This report documents the methodology used to transform our primary datasets into integrated analytical datasets that enable multivariate regression analysis and temporal trend assessment.

## Population Classification

We classified districts into three categories based on urban percentage:

$$
\text{Urban-Rural Classification} = 
\begin{cases}
    \text{rural},      & \text{if } \text{urban\_percentage} < 15 \\
    \text{peri-urban}, & \text{if } 15 \leq \text{urban\_percentage} < 50 \\
    \text{urban},      & \text{if } \text{urban\_percentage} \geq 50
\end{cases}
$$

This approach provides a more nuanced understanding of the urbanization gradient across Rwanda compared to the binary classification used initially.

## Road Network Analysis

Using road network GeoJSON data and administrative boundaries shapefile, we performed spatial analysis to extract road metrics at the district level. We transformed coordinates to UTM Zone 36S (EPSG:21096) for accurate distance measurements and classified roads based on "highway" attributes to distinguish major roads (motorways, trunks, primary, secondary) from local roads.

Road density was calculated as:

$$\text{Road Density} = \frac{\text{Total Road Length (m)}}{\text{District Area (km²)}}$$

The road coverage index represents the proportion of a district's area within 500m of any road:

$$\text{Road Coverage Index} = \min\left(\frac{\text{Area within 500m of roads}}{\text{Total District Area}}, 1.0\right)$$

We created a major roads exposure index that combines proximity to major roads with their presence:

$$\text{Major Roads Exposure Index} = 0.7 \times \text{Proximity Factor} + 0.3 \times \text{Major Roads Ratio}$$

Where:
- Proximity Factor = $0.5 \times \frac{\text{Area within 1km}}{\text{Total Area}} + 0.3 \times \frac{\text{Area within 5km}}{\text{Total Area}} + 0.2 \times \frac{\text{Area within 10km}}{\text{Total Area}}$
- Major Roads Ratio = $\frac{\text{Length of Major Roads}}{\text{Total Road Length}}$

For each district, we calculated the percentage of area within specific distances from major roads:

$$\text{Pct Within } d\text{km} = \min\left(\frac{\text{Area within } d\text{ km of major roads}}{\text{Total District Area}} \times 100, 100\right)$$

Where $d$ = 1, 5, and 10 kilometers.

## AQI Data Processing

Since AQI data was at sector level while other datasets were at district level, we aggregated using a hierarchical approach. First, we calculated monthly district averages:

$$\text{AQI}_{d,y,m} = \frac{1}{n} \sum_{i=1}^{n} \text{AQI}_{i,d,y,m}$$

Where $\text{AQI}_{i,d,y,m}$ is the AQI value for sector $i$ in district $d$ in year $y$ and month $m$.

From these monthly averages, we derived district-level statistics including mean, median, standard deviation, and coefficient of variation:

$$\text{AQI CV}_d = \frac{\sigma_d}{\mu_d}$$

For temporal trend analysis, we calculated average year-over-year changes:

$$\text{YoY Pct Change}_d = \frac{1}{Y-1} \sum_{y=2}^{Y} \frac{\text{AQI}_{d,y} - \text{AQI}_{d,y-1}}{\text{AQI}_{d,y-1}} \times 100$$

## Data Integration and Standardization

We integrated all processed datasets into a comprehensive district-level dataset by merging road metrics, AQI statistics, and population indicators. For multivariate regression analysis, we standardized key numerical variables:

$$X_{standardized} = \frac{X - \mu_X}{\sigma_X}$$

This ensures all variables have mean=0 and standard deviation=1, preventing scaling issues in regression models.

## Limitations

Our data processing methodology has several important limitations. The sector-to-district aggregation of AQI data loses spatial heterogeneity, potentially masking localized pollution hotspots. Simple averaging doesn't account for population density variations, underweighting pollution exposure in densely populated areas. The road metrics rely on OpenStreetMap data completeness, which may vary across regions. The urban/rural/peri-urban categorization using static thresholds doesn't capture urbanization's continuous nature. Road exposure metrics assume uniform pollution dispersion without accounting for wind patterns, topography, or actual traffic volumes. Temporal analysis might be influenced by the COVID-19 pandemic during 2020-2021. Finally, our district-level analysis assumes administrative boundaries align with pollution patterns, which may not reflect real-world atmospheric dynamics.