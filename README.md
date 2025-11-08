# Jiahang Luo

## Description

I will build a Democracy Trajectory Simulator: an interactive, simulation-driven visualization that lets users explore “what-if” scenarios for a country’s democracy level over the next 10 years. Users can set assumptions about GDP per-capita growth, inequality changes, and the probability of shocks like war, then run the simulation to see a fan chart (quantiles) and compare trajectories against peer groups (neighbors, income peers). The goal is to help audiences reason about plausible ranges to connect economic and institutional assumptions to potential democratic trajectories.

## Technical Plan

Path: Option A : The core experience is a single, centerpiece simulation with lots of options. 

Libraries: D3.js for the main fan-chart (quantiles), small multiples, and transitions.
Python for data process and fit a simple model to export coefficients

Examples:
NYT “You Draw It” interactives
www.nytimes.com/interactive/2015/05/28/upshot/you-draw-it-how-family-income-affects-childrens-college-chances.html

FlowingData – “A Day in the Life of Americans.
https://flowingdata.com/2015/12/15/a-day-in-the-life-of-americans/



## Mockup

<img width="1126" height="582" alt="image" src="https://github.com/user-attachments/assets/d9f6efb1-488b-4dfa-908f-54a68eb196e4" />

## Data Sources

### Data Source 1: V-Dem

URL: https://v-dem.net/data/the-v-dem-dataset/

Size: 27913 rows, 4607 columns

The V-Dem dataset is a global country–year panel containing multiple headline democracy indices (for example, v2x_libdem for liberal democracy and v2x_polyarchy for electoral democracy) plus dozens of component indicators such as participation, civil liberties, and judicial constraints. I downloaded the CSV, examined the headers and a random sample of rows to verify the expected variables and check for missing values. To maintain a temporally consistent panel and avoid country name changes and reduce irregular gaps, I restricted the project to the 1995–2024 slice, which yields a complete and stable dataset for the visualization. 


### Data Source 2: World Bank Economics growth

URL: https://data.worldbank.org/indicator/NY.GDP.MKTP.KD.ZG?end=2024&start=2024&view=map

Size: 266 rows, 70 columns

The World Bank GDP growth indicator reports the annual percent change in GDP at market prices (constant prices); I checked the number of missing observations and inspected their corresponding time ranges to assess the series’ coverage for the country–year analysis.


## Questions

{Numbered list of questions for course staff, if any.}

1.  For a public-facing explorable, should I tell them how the model works and which is the one I choose?
2.  Is there any other way I can add more interactivity into this?
3.
