# Democracy Trajectory Simulator
### Jiahang Luo
## Description

This project is an interactive "Democracy Trajectory Simulator" that allows users to explore "what-if" scenarios for a country's political future. By adjusting key assumptions—specifically GDP growth, equality, rule of law, and freedom of expression—users can simulate plausible ranges for the V-Dem Liberal Democracy Index over the next 10 years.

The visualization uses a dynamic panel model and Monte Carlo simulations (1,000 runs) to generate a fan chart, visually representing the uncertainty of the predictions. Key features include a "Comparison Mode" to overlay different scenarios and historical presets (such as a "US New Deal" or "China Economic Miracle") to help users contextualize the data.

<img width="778" height="1474" alt="final" src="https://github.com/user-attachments/assets/11886583-49e2-4823-9823-26e0c585ce14" />


## Data Sources

### Data Source 1: V-Dem

URL: https://v-dem.net/data/the-v-dem-dataset/

Size: 27913 rows, 4607 columns

The V-Dem dataset is a global country–year panel containing multiple headline democracy indices (for example, v2x_libdem for liberal democracy and v2x_polyarchy for electoral democracy) plus dozens of component indicators such as participation, civil liberties, and judicial constraints. I downloaded the CSV, examined the headers and a random sample of rows to verify the expected variables and check for missing values. To maintain a temporally consistent panel and avoid country name changes and reduce irregular gaps, I restricted the project to the 1995–2024 slice, which yields a complete and stable dataset for the visualization. 


### Data Source 2: World Bank Economics growth

URL: https://data.worldbank.org/indicator/NY.GDP.MKTP.KD.ZG?end=2024&start=2024&view=map

Size: 266 rows, 70 columns

The World Bank GDP growth indicator reports the annual percent change in GDP at market prices (constant prices); I checked the number of missing observations and inspected their corresponding time ranges to assess the series’ coverage for the country–year analysis.
