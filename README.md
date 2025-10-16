# Minimizing Overall Cost of Transported Goods Over Long-Distance Distribution

## Project Overview

This project applies **Operations Research techniques** to solve a real-world transportation problem for **Transcom Beverage Limited (TBL)**, the exclusive PepsiCo franchise in Bangladesh. The objective is to minimize the total transportation cost of distributing beverages from manufacturing facilities to regional warehouses across the country.

**Course:** IPE 307 - Operations Research  
**Institution:** Bangladesh University of Engineering and Technology (BUET)  
**Date:** March 2023  
**Team Members:** Md. Tawfique Ihsan (1908040), Mohiuddin Adnan (1908042), Sadat Iqbal Priom (1908043)

---

## Problem Statement

Transcom Beverage Limited operates:
- **3 Manufacturing Sites:** Konabari, Bagher Bazar (both in Gazipur), and Chittagong
- **5 Regional Warehouses:** Sylhet, Bogura, Chittagong, Khulna, and Gazipur

The challenge is to determine the optimal allocation of products from factories to warehouses to minimize total transportation costs while satisfying:
- Supply constraints at each factory
- Demand requirements at each warehouse

### Key Constraints
- **Total Supply:** 215,000 cartoons/day (45,000 + 90,000 + 80,000)
- **Total Demand:** 252,000 cartoons/day (creating an unbalanced transportation problem)
- **Transportation:** Uses 16ft covered vans (short distance) and 22ft covered vans (long distance >120km)
- **Cost Structure:** Includes per-kilometer transportation costs and toll road expenses

---

## Methodology

### 1. Mathematical Formulation
The problem is formulated as a **Linear Programming Problem (LPP)** with:
- **Decision Variables:** x_ij (amount transported from factory i to warehouse j)
- **Objective Function:** Minimize total transportation cost Z = Σ(c_ij × x_ij)
- **Constraints:** 
  - Supply constraints (equality): Total shipments from each factory = factory capacity
  - Demand constraints (inequality): Total shipments to each warehouse ≤ warehouse demand

### 2. Solution Approach
- **Initial Basic Feasible Solution (BFS):** Russell's Approximation Method
- **Optimization Algorithm:** Transportation Simplex Method
- **Verification Tool:** Microsoft Excel Solver

---

## Data Collection

### Distance Matrix (in kilometers)
|           | Sylhet | Bogura | Chittagong | Khulna | Gazipur |
|-----------|--------|--------|------------|--------|---------|
| Konabari  | 232    | 157    | 292        | 250    | 21      |
| Bagher Bazar | 235 | 184    | 311        | 270    | 40      |
| Chittagong | 378   | 441    | 20         | 450    | 274     |

### Transportation Cost Matrix (Tk per cartoon)
|           | Sylhet | Bogura | Chittagong | Khulna | Gazipur | Supply |
|-----------|--------|--------|------------|--------|---------|--------|
| Konabari  | 35,480 | 23,380 | 43,280     | 38,900 | 2,940   | 45,000 |
| Bagher Bazar | 35,900 | 27,160 | 45,940  | 41,700 | 5,600   | 90,000 |
| Chittagong | 52,920 | 62,040 | 2,800     | 67,300 | 39,960  | 80,000 |
| **Demand** | **52,000** | **35,000** | **50,000** | **50,000** | **65,000** | **252,000** |

**Note:** Costs include both distance-based transportation (140 Tk/km for 1.5-ton van) and toll road expenses.

---

## Optimal Solution

The optimization yielded the following allocation:

| From | To | Cartoons |
|------|-----|----------|
| Bagher Bazar | Sylhet | 22,000 |
| Bagher Bazar | Khulna | 8,000 |
| Bagher Bazar | Gazipur | 60,000 |
| Konabari | Bogura | 35,000 |
| Konabari | Khulna | 10,000 |
| Chittagong | Sylhet | 30,000 |
| Chittagong | Chittagong | 50,000 |

### Key Insights
- **Bagher Bazar** supplies primarily to nearby Gazipur (low cost) and partially to Sylhet and Khulna
- **Konabari** efficiently serves Bogura and Khulna
- **Chittagong factory** serves Chittagong warehouse directly (minimal cost) and contributes to Sylhet demand
- Several factory-warehouse pairs have zero allocation in optimal solution despite lower individual costs—this is because the algorithm optimizes the **entire system** holistically

---

## Technical Details

### Russell's Approximation Method
This heuristic provides a good initial basic feasible solution by:
1. Computing penalties (ui and vj) for each row and column
2. Calculating Δij = cij - ui - vj for unallocated cells
3. Selecting the cell with maximum negative Δij for allocation
4. Iterating until all supply/demand is satisfied

### Transportation Simplex Method
- Specialized algorithm for transportation problems (more efficient than general simplex)
- Uses stepping stone method or MODI (Modified Distribution) method for optimality testing
- Iteratively improves solution until optimal allocation is found

---

## Project Structure

```
├── 1908040_1908042_1908043_IPE-307-term-Project.pdf    # Complete project report
├── README.md                                             # This file
└── [Excel file - currently unavailable]                 # Solver implementation
```

### ⚠️ Important Note: Missing Excel File

**The original Excel Solver file used for this project is currently unavailable.** The file contained:
- Complete transportation cost matrix
- Decision variable cells (x_ij allocations)
- Excel Solver configuration with objective function and constraints
- Optimal solution output

We apologize for any inconvenience. If the Excel file is recovered, this repository will be updated.

---

## Learning Outcomes

Through this project, we gained practical experience in:
- Formulating real-world problems as mathematical optimization models
- Applying transportation problem algorithms (Russell's, Transportation Simplex)
- Using Excel Solver for linear programming
- Interpreting optimal solutions in business context
- Understanding supply chain optimization challenges

---

## Acknowledgments

- **Dr. Kais Bin Zaman**, Professor, Department of IPE, BUET - Course instructor and project supervisor
- **Mr. Romel**, Manager, Chittagong Factory, PepsiCo Inc. - Provided critical data and industry insights
- Factory co-workers who assisted in data collection
- IPE classmates for collaboration and discussion

---

## References

- Operations Research textbook concepts (Transportation Problem, Linear Programming)
- PepsiCo Bangladesh (Transcom Beverage Limited) operational data
- Excel Solver documentation for optimization

---

## Contact

For questions about this project, please contact:
- Md. Tawfique Ihsan - 1908040
- Mohiuddin Adnan - 1908042  
- Sadat Iqbal Priom - 1908043

**Department of Industrial and Production Engineering**  
Bangladesh University of Engineering and Technology (BUET)

---

## License

This project is for academic purposes. All data is used with permission from Transcom Beverage Limited for educational analysis only.

