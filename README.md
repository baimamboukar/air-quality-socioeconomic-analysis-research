# Mapping Socioeconomic Air Quality Disparities In Rwanda Using Sentinel-5P TROPOMI Data In Google Earth Engine

## Introduction

This study examines the relationship between air quality and socioeconomic status using high-resolution data from the Sentinel-5P satellite and sector-level poverty indicators. By calculating an Air Quality Index (AQI) and correlating it with poverty metrics, the study aims to identify disparities in pollution exposure. Leveraging Google Earth Engine’s cloud computing, the spatial-temporal analysis will reveal whether economically disadvantaged populations face higher pollution levels. The findings will provide evidence for policymakers and urban planners to implement targeted air quality management strategies, ensuring equitable environmental policies and sustainable development in Rwanda.

---

## Table of Contents

1. [Background](#background)
2. [Objectives](#objectives)
3. [Methodology](#methodology)
4. [Research Question](#research-question)
5. [How to Use this Repository](#how-to-use-this-repository)
---

## Background

Rwanda has experienced rapid economic growth and urbanization, which has led to increasing air pollution levels. Studies indicate that ambient air pollution is a growing contributor to non-communicable diseases (NCDs) such as cardiovascular disease (CVD), especially in low-income communities. Despite global advancements in air quality monitoring, there is limited research on how socioeconomic disparities influence exposure to air pollution in Rwanda.

---

## Objectives

The primary objectives of this study are:

- To quantify air pollution levels across Rwanda using Sentinel-5P TROPOMI satellite data.
- To calculate an Air Quality Index (AQI) for various regions.
- To analyze the correlation between AQI and socioeconomic indicators, such as poverty rates.
- To provide actionable insights for policymakers to address environmental inequalities.

---

## Methodology

This project involves the following steps:

1. **Data Acquisition**:
   - Retrieve Sentinel-5P TROPOMI data for pollutants such as NO₂, CO, and PM2.5 using Google Earth Engine.
   - Collect socioeconomic data at the sector level from national statistics.

2. **Data Processing**:
   - Preprocess satellite imagery to extract pollutant concentrations.
   - Calculate AQI values based on established standards.

3. **Correlation Analysis**:
   - Perform statistical analysis to identify relationships between AQI and poverty indicators.

4. **Visualization**:
   - Create spatial maps of AQI and socioeconomic disparities using GIS tools.

---

## Research Questions

How does air pollution exposure vary by socioeconomic status in Rwanda, are vulnerable communities more affected?

## How to Use this Repository

1. Clone the repository:
- Clone this repository to your local machine using Git: git clone https://github.com//Illustre13/air-quality.git
2. Install Required Dependencies:
- Install necessary libraries and packages using pip: pip install -r requirements.txt
3. Set Up Google Earth Engine (GEE) Account:
- Create a GEE account if you don't already have one.
- Install the GEE Python API using pip:
  ```
  pip install earthengine-api
  ```
- Authenticate your GEE account using the API.


$$
\text{AQI} = 100 \times \max_{X \in \{\text{SO}_2, \text{CO}, \text{NO}_2, \text{O}_3, \text{CH}_4, \text{Aerosol}\}} \left( \frac{\text{measured}_X}{\text{WHO threshold}_X} \right)
$$
