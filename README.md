Spatial Analysis of Baltimore Homicides
Course: ERHS 535 - R Programming for Research
Assignment: Homework #5
Due Date: December 1, 2024
Author: Eliud Rivas Hernandez

# Project Overview
This project conducts a spatial analysis of homicide data in Baltimore, MD, from 2007-2017, examining the geographic distribution of solved and unsolved cases across different racial groups. The analysis uses R's sf package for spatial operations and tigris for downloading Census geographic boundaries.
Research Questions

How are homicides spatially distributed across Baltimore?
Are there geographic differences between solved and unsolved homicides?
Do different racial groups experience homicides in different geographic areas?

# Data Sources
## Primary Data
Washington Post Homicide Database (2007-2017)
**Source:** GitHub Repository.    
**File:** homicide-data.csv
**Description:** Comprehensive database of over 52,000 criminal homicides in 50 large U.S. cities
**Key variables:** city, state, victim demographics, case disposition, latitude/longitude



# Geographic Data
U.S. Census Bureau TIGER/Line Shapefiles (2020)
Downloaded via tigris R package
**Geography:** Census tracts for Baltimore City, MD (FIPS: 24510)
**Purpose:** Provide geographic context and boundaries for spatial analysis



# Key Findings

**Sample Size:** Analysis includes 2,827 homicides in Baltimore from 2007 to 2017
**Clearance Rate:** Approximately 35-40% of cases remain unsolved
**Racial Disparities:** Black victims represent the overwhelming majority of homicide victims
**Spatial Patterns:** Clear geographic clustering with concentrated areas of violence
**Solved vs. Unsolved:** Different spatial patterns between case clearance rates

# Methods
## Spatial Analysis Approach

## Data Preparation

-Filtered the Washington Post data for Baltimore, MD
-Classified cases as "Solved" or "Unsolved" based on disposition
-Used forcats::fct_lump() to identify the top 3 racial groups


## Spatial Framework

-Converted homicide data to sf spatial object (WGS84/EPSG:4326)
-Downloaded Baltimore City census tracts using the tigris package
-Verified spatial alignment between points and boundaries


## Visualization

-Created faceted maps showing solved vs. unsolved cases
-Used color to distinguish the top 3 racial groups
-Overlaid homicide points on census tract boundaries



# Key R Packages

-**tidyverse:** Data manipulation and visualization
-**sf:** Simple features for spatial data
-**tigris:** Download Census TIGER/Line shapefiles
-**forcats:** Factor manipulation (fct_lump)
-**viridis:** Color scales for accessibility


# Download the data

Download homicide-data.csv from the Washington Post GitHub
Place in data/ directory


# Limitations and Considerations

**Data Currency:** Analysis uses data through 2017; patterns may have changed
**Case Classification:** "Solved" includes only arrests, not convictions
**Geographic Precision:** Coordinates may be approximate in some cases
**Racial Categories:** Census categories may not reflect individual identity
**Temporal Aggregation:** Analysis pools 10 years of data, masking temporal trends

# References    

The Washington Post. (2018). "Murder with Impunity: Where killings go unsolved."
Article Link
U.S. Census Bureau. (2020). TIGER/Line Shapefiles.
Census Geographic Data
Walker, K. (2023). tigris: Load Census TIGER/Line Shapefiles. R package version 2.0.4.
Pebesma, E. (2018). Simple Features for R: Standardized Support for Spatial Vector Data.
The R Journal, 10(1), 439-446.


# License    
This project is submitted as coursework for ERHS 535 at Colorado State University. 
The underlying homicide data is provided by The Washington Post and is subject to their terms of use.

