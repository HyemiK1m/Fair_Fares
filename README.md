# Fair Fares for Vehicle Sharing Systems
_Adam N. Elmachtoub and Hyemi Kim_

This repository contains the source code to reproduce the findings presented in the research paper titled "Fair Fares for Vehicle Sharing Systems". For an in-depth understanding, please refer to the [full paper](link).

## Experimental Setup
Some code files utilize the **Pyomo** library to address non-convex optimization challenges. We employ the **Couenne** (global solver) and **Ipopt** (local solver) optimization solvers. While the codebase is tailored for usage with **Colab**, you have the flexibility to execute it locally by setting up the necessary libraries, such as pyomo.

## Theoretical Analysis

### Notation
- $N$: Number of locations (nodes)
- $K$: Number of vehicles (units)

### Characterized_Region.ipynb (Figure 1 & 4)
Visualizes characterized regions demonstrating price fairness implications for both linear and exponential demand models.

### Stylized_Linear.ipynb (Figure 2)
- Fairness Metrics: Price & Access
- Demand Function: Linear Demand
- $N = 2$, $K = 1$

### Stylized_Linear_K.ipynb (Figure 3 & 7)
- Fairness Metrics: Price & Access
- Demand Function: Linear Demand
- $N = 2$, $K \geq 1$

### Stylized_Exponential.ipynb (Figure 5 & 6 & 8)
- Fairness Metrics: Price & Access
- Demand Function: Exponential Demand
- $N = 2$, $K \geq 1$

### Stylized_Grid.ipynb (Figure 2, 3, 5, 6, 7, 8)
- Fairness Metrics: Price & Access
- Demand Function: Linear & Exponential Demand
- $N = 2$, $K = 1$
- Perform a grid search on the stylized model without utilizing a solver

## Computational Analysis & Approximation

### Computational_Exponential.ipynb (Figure 9 & 10)
- Fairness Metrics: (trip/origin based) Price & Access
- Demand Function: Exponential Demand
- $N = 3$, $K \geq 1$

### Exponential_Approximation.ipynb & Exponential_Grid_Search (Figure 11 & 19)
- Get an approximate solutions from _Exponential_Approximation.ipynb_
- Using the approximated solutions, run _Exponential_Grid_Search.ipynb_ in _Grid_Search_

[//]: # (### Logistic_Approximation.ipynb)
[//]: # ()
[//]: # (- Fairness Metrics: &#40;trip / origin based&#41; Price & Access)
[//]: # (- Demand Function: Logistic Demand)
[//]: # (- $N \geq 2$, $K \geq 1$)
[//]: # (- Approximation Framework)

## Case Study

### Important Notes

- Adjust the file location within the relevant code sections.
- Download the required [data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page) based on your desired analysis timeframe:
  - Yellow Taxi Trip Records (PARQUET)
  - Green Taxi Trip Records (PARQUET)
  - High Volume For-Hire Vehicle Trip Records (PARQUET)
  - Taxi Zone Lookup Table (CSV)
- Organize downloaded files into the "Case_Study/Data" folder.
- To visualize outcomes, download _Taxi Zone Shapefile (PARQUET)_ and include the following files:
  - taxi_zones.shx
  - taxi_zones.shp

### HVFHV_preprocessing_logistic.ipynb (Table 3-10 and Figure 21)

- Adjust the timeframe within the code as needed:
```python
time_start = "2023-03-03 18:00:00"
time_end = "2023-03-03 20:00:00"
```
- Output: data_dictionary_logistic.pkl

### Case_Study.ipynb (Figure 14-18)
Update the pwd (path) to load _data_dictionary_logistic.pkl_.
