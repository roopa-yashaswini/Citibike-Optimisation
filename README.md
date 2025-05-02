# 🚲 Optimization at Citibike – Integer Programming for Inventory Rebalancing

## 🧠 Project Overview

This project applies **operations research and optimization techniques** to a real-world bikesharing scenario at **Citibike NYC**. During peak hours, many stations suffer from "stock-outs" where no bikes are available, leading to lost customers. According to internal analysis, **a 4% efficiency gain could turn Citibike profitable**.

To address this, we use **integer programming (via PuLP in Python)** to develop a bike inventory rebalancing plan that minimizes shortages and logistics costs across hundreds of stations.

---

## 📊 Business Problem

- 20% of Citibike stations face stock-outs at peak times.
- Riders abandon the system when no bikes are available.
- Our goal is to **redistribute existing bikes** to meet demand more effectively without adding new inventory.

---

## ⚙️ Technical Approach

### Data Loading & Visualization
- Loaded `demand.csv`, `supply.csv`, and `distances.csv`.
- Visualized stock-outs using heatmaps and bar charts.
- Identified over-supplied vs under-supplied stations.

### Base Optimization Model
- Used `Gurobi` to define decision variables `x[i][j]` for bikes moved from station `i` to station `j`.
- Objective: **minimize unmet demand** (stock-outs).
- Constraints:
  - Bikes sent ≤ bikes available
  - Bikes received ≤ demand
  - Only existing inventory can be moved (no new bikes introduced)

### Model Enhancements
- Added:
  - **Truck Capacity Constraints** (maximum bikes moved per station)
  - **Distance-based Cost Minimization** (penalize longer routes)
  - **Fairness constraints** to balance service across boroughs

### Scenario Evaluation
- Compared the current setup with optimized redistribution
- Achieved up to **60% reduction in stock-outs** under tight constraints
- Plotted maps showing original vs rebalanced supply

---

## 📦 File Structure

```
.
├── Workshop 2 -- Optimization at Citibike.ipynb   # Full notebook with analysis
├── data
└── README.md
```

---

## 📈 Results

- Formulated a practical integer programming model tailored to Citibike's operations
- Cut station stock-outs by 50–60% using only existing inventory
- Illustrated clear ROI for optimization-based decision making

---

## 🔧 Tools Used

- Python (Jupyter)
- Libraries: `pandas`, `matplotlib`, `seaborn`, `PuLP`
- Linear/Integer Programming: `gurobi`
- Data visualization (station maps, network graphs)

---

## 📌 How to Reproduce

1. Install dependencies:
```bash
pip install pandas matplotlib seaborn pulp
```

2. Open the notebook:
```bash
jupyter notebook "Workshop 2 -- Optimization at Citibike.ipynb"
```

3. Run all cells to replicate data analysis and optimization outputs.

