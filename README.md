# Fair Fares for Vehicle Sharing Systems
_Adam N. Elmachtoub and Hyemi Kim_

This repository contains the source code to reproduce the findings presented in the research paper titled "Fair Fares for Vehicle Sharing Systems". For an in-depth understanding, please refer to the [full paper](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4699813).

## Experimental Setup
Some code files utilize the **Pyomo** library to address non-convex optimization challenges. We employ the **Couenne** (global solver) and **Ipopt** (local solver) optimization solvers. While the codebase is tailored for usage with **Colab**, you have the flexibility to execute it locally by setting up the necessary libraries, such as pyomo.

## Theoretical Analysis

### Notation
- $N$: Number of locations (nodes)
- $K$: Number of vehicles (units)

### Characterized_Region.ipynb (Figure 1 & 4)
Visualizes characterized regions demonstrating price fairness implications for both linear and exponential demand models.

### Stylized_Linear.ipynb (Figure 2 & 3)
- Fairness Metrics: Price & Access
- Demand Function: Linear Demand
- $N = 2$, $K = 1$

### Stylized_Exponential.ipynb (Figure 5 & 6 & 12; Figure 7 in Appendix)
- Fairness Metrics: Price & Access
- Demand Function: Exponential Demand
- $N = 2$, $K \geq 1$

### Travel_time.ipynb (Figure 7 & 8)
- Fairness Metrics: Price & Access
- Demand Function: Linear Demand
- $N = 2$, $K = 1$
- travel time >= 0

### Repositioning.ipynb (Figure 9 & 10)
- Fairness Metrics: Price & Access
- Demand Function: Linear Demand
- $N = 2$, $K = 1$
- Reposition is available

### Stylized_Linear_K.ipynb (Figure 11; Figure 6 in Appendix)
- Fairness Metrics: Price & Access
- Demand Function: Linear Demand
- $N = 2$, $K \geq 1$

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

### HVFHV_preprocessing_logistic.ipynb (Table 1-5 and Figure 16 in Appendix)

- Adjust the timeframe within the code as needed:
```python
time_start = "2023-03-03 18:00:00"
time_end = "2023-03-03 20:00:00"
```
- Output: data_dictionary_logistic.pkl

### Case_Study.ipynb (Figure 13 & 14; Table 1 & 2)
- Update the pwd (path) to load _data_dictionary_logistic.pkl_.

## Computational Analysis & Approximation

### Computational_Linear.ipynb & Computational_Linear_Visualize_Results.ipynb (Figure 8 & 9 in Appendix)
- Run _Computational_Linear.ipynb_ for each range of piece-wise linear demand (denoted as z)
- Visualize the result using _Computational_Linear_Visualize_Results.ipynb_
- The derived results are in the Computational_Linear_Results.zip

### Computational_Exponential.ipynb (Figure 10 & 11 in Appendix)
- Fairness Metrics: (trip/origin based) Price & Access
- Demand Function: Exponential Demand
- $N = 3$, $K \geq 1$

### Heuristic_Exponential.ipynb & Exponential_Grid_Search (Figure 12 & 14 in Appendix)
- Get an approximate solution from _Heuristic_Exponential.ipynb_
- Using the approximated solution, run _Exponential_Grid_Search.ipynb_ in _Grid_Search_

## The Remaining Figures in Appendix
- Characterized_Region_Travel_time.ipynb: Figure 1
- Travel_time_K: Figure 2 & 3
- Repositioning_K: Figure 4 & 5

## Case Study with different timeframe in Appendix
- Change the timeframe and follow the same procedure as in the **Case Study**
