# Fair Fares for Vehicle Sharing Systems

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
- (brute-force version) 

### Stylized_Linear_K.ipynb (Figure 3)

- Fairness Metrics: Price & Access
- Demand Function: Linear Demand
- $N = 2$, $K \geq 1$
- (brute-force version) 

### Stylized_Exponential.ipynb (Figure 5 & 6)

- Fairness Metrics: Price & Access
- Demand Function: Exponential Demand
- $N = 2$, $K \geq 1$
- (brute-force version) 

## Computational Analysis & Approximation

### Computational_Exponential.ipynb

- Fairness Metrics: (trip/origin based) Price & Access
- Demand Function: Exponential Demand
- $N = 3$, $K \geq 1$

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
- Organize downloaded files into the "Data" folder.
- To visualize outcomes, obtain and include the following file:
  - Taxi Zone Shapefile (PARQUET)

### HVFHV_preprocessing_logistic.ipynb

- Adjust the timeframe within the code as needed:
```python
time_start = "2023-03-03 18:00:00"
time_end = "2023-03-03 20:00:00"
```
- Output: data_dictionary_logistic.pkl

### Case_Study.ipynb
Update the pwd (path) to load _data_dictionary_logistic.pkl_.
