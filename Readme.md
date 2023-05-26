# Proposal for Semester Project

**Patterns & Trends in Environmental Data / Computational Movement
Analysis Geo 880**

| Semester:      | FS23                                     |
|:---------------|:---------------------------------------- |
| **Data:**      | Posmo - GPS locations- walking  mode|
| **Title:**     | Differences in walking patterns between functional- and recreational dog walks                |
| **Student 1:** | Margarita Kessler                        |
| **Student 2:** | Mirjam Nötzli                        |

## Abstract 
<!-- (50-60 words) -->
The project aims to analyze our walking patterns as dog owners. We are interested in investigating how the walking patterns differ between recreational- and functional-dog walks (the minimal requirement for the dog’s well-being). We will use our GPS data to evaluate our movement patterns in terms of behavior, distance covered, weather, duration, speed, and land use type. 

## Research Questions
<!-- (50-60 words) -->
•	How do recreational dog-walks differ from functional-dog walks?
•	Are functional dog walks more similar than recreational dog walks?
•	Are recreational dog walks influenced by weather (precipitation), i.e is the distance affected by precipitation?
•	How do the recreational dog walking patterns differ temporally? How do the patterns differ between morning-/afternoon-/evening walks?

## Results / products
<!-- What do you expect, anticipate? -->
•	Prediction 1: Functional dog walks take place in very proximity to the house, and have a shorter duration, higher pace, and cover a shorter distance. Recreational dog walks take place at further distances from the house and have a longer duration, shorter pace, and longer duration.  
•	Prediction 2: On rainy days the dog walks tend to be shorter in duration, cover a shorter distance, and have a higher pace. On non-rainy days dog walks tend to last longer, cover a longer distance, and have a slower pace. 
•	Prediction 3: Morning walks are longer than afternoon and evening walks. 

## Data
<!-- What data will you use? Will you require additional context data? Where do you get this data from? Do you already have all the data? ->
GPS locations of two dog owners between April-June 2023 (Data available from Posmo). 
Local weather (mostly precipitation yes/no) --> not sure where to get this data from
Land use data (GIS Portal Kanton Zürich?)
Road and trail network data- (swissTLM3D)
Digital terrain model (Slope) Maybe?

## Analytical concepts
<!-- Which analytical concepts will you use? What conceptual movement spaces and respective modelling approaches of trajectories will you be using? What additional spatial analysis methods will you be using? -->
Conceptual movement spaces:
The space model accommodating the movement of the objects is network space/Euclidian homogeneous space.
Property of the movement:
Constrained to roads and trails.
Observation perspective: Lagrangian (GPS locations).
Semantic level of interest: Fix, move, segment, weather, land-use cover (green/no green).
-Data structures: 
• Vectors: Roads and trails network, land use data, observation points. 
• Raster: DTM 
The movement patterns of the dog walks will be classified into axial routes, radial routes, partial loops, and full loops according to Jamhawi et al. 2023. 

## R concepts
<!-- Which R concepts, functions, packages will you mainly use. What additional spatial analysis methods will you be using? -->
Pre-processing: 
•	We will join the two datasets and handle them as spatial data. The joined dataset will be filtered (only GPS locations while walking will be kept). 
•	EDA
•	Select granularity (temporal)
•	Trajectory segmentation (remove static points) and then assign a new variable: trajectory ID.
•	Calculate movement parameters: time lag, distance, and speed.
•	A new variable will be assigned to each trajectory: Rain (TRUE/FALSE). 
•	Use the spatial join function to assign land-use data to each point/trajectory?
•	Visualization of individual trajectories to assign movement behavior. 

Analysis:
•	Calculate similarity measures among functional dog walks (we will define a threshold distance for definition, probably <30min)/  recreational dog walks. 
•	Evaluate differences in speed, distance covered, duration between functional and recreational dog walks, and between walks in good vs bad weather. 

R-Packages
•	sf
•	tidyverse (readr, inner-join, filter, select, mutate)
•	similaritymeasures
•	ggplot2

## Risk analysis
<!-- What could be the biggest challenges/problems you might face? What is your plan B? -->
Small trails used for dog walks may not be digitally available. 
GPS locations within the forest may not be accurate.
Weather data might not be available. If not, then we would focus on our other research questions-

## Questions? 
<!-- Which questions would you like to discuss at the coaching session? -->
Where could we get the weather data from?
Should we look at the type of land use and the digital terrain model?
