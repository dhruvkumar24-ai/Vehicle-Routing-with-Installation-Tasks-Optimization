# 🚛 Vehicle Routing with Installation Tasks Optimization
### VRPTW · MILP · Branch-and-Cut · CPLEX · Python

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)
![CPLEX](https://img.shields.io/badge/IBM_CPLEX-Optimizer-054ADA?style=flat-square)
![MILP](https://img.shields.io/badge/Model-MILP-orange?style=flat-square)
![Status](https://img.shields.io/badge/Status-Exact_Solutions_Found-brightgreen?style=flat-square)
![Course](https://img.shields.io/badge/IIT_Kanpur-OR_Course_Project-red?style=flat-square)

---

## 🧩 Problem Statement

Real-world delivery operations aren't just about routing — vehicles must also **schedule installation tasks** at customer sites within strict time windows. This project solves the **Vehicle Routing Problem with Time Windows (VRPTW)** extended with **installation scheduling**, modeled as a **Mixed Integer Linear Program (MILP)** and solved to exact optimality using **IBM CPLEX**.

> *"Find the minimum-cost set of routes and task schedules such that all customers are visited within their time windows and all installations are completed without overlap."*

---

## ⚙️ Methodology

```
Problem Formulation
        │
        ▼
  MILP Model (VRPTW + Installation Scheduling)
        │
        ├─── Decision Variables: Route assignments, visit times, task sequences
        ├─── Objective: Minimize total operational cost (distance + time)
        └─── Constraints:
                ├── Time Window feasibility
                ├── Miller-Tucker-Zemlin (MTZ) subtour elimination
                ├── Installation task non-overlap
                └── Vehicle capacity
        │
        ▼
  Branch-and-Cut (IBM CPLEX)
        │
        ▼
  Exact Optimal Solutions (15 benchmark instances)
        │
        ▼
  Dantzig-Wolfe Decomposition (ongoing — scalability improvement)
```

---

## 🔑 Key Highlights

| Feature | Detail |
|---|---|
| **Model Type** | Mixed Integer Linear Program (MILP) |
| **Solver** | IBM CPLEX via Python API |
| **Subtour Elimination** | Miller-Tucker-Zemlin (MTZ) constraints |
| **Algorithm** | Branch-and-Cut |
| **Instances Solved** | 15 benchmark instances (exact solutions) |
| **Scalability Work** | Dantzig-Wolfe Decomposition (in progress) |

---

## 📁 Repository Structure

```
📦 vrptw-installation-optimization/
├── 📂 model/
│   ├── vrptw_milp.py          # Core MILP formulation
│   ├── mtz_constraints.py     # MTZ subtour elimination
│   └── installation_sched.py  # Installation task constraints
├── 📂 solver/
│   ├── cplex_solver.py        # IBM CPLEX integration
│   └── dantzig_wolfe.py       # Decomposition (WIP)
├── 📂 instances/
│   └── benchmark_data/        # 15 test instances
├── 📂 results/
│   └── solution_plots/        # Route visualizations
├── requirements.txt
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install cplex docplex matplotlib networkx pandas numpy
```
> IBM CPLEX Academic License required. Available free via [IBM Academic Initiative](https://www.ibm.com/academic).

### Run
```bash
# Solve a benchmark instance
python solver/cplex_solver.py --instance instances/benchmark_data/instance_01.json

# Visualize routes
python results/plot_routes.py --solution results/solution_01.json
```

---

## 📊 Results

- ✅ **Exact optimal solutions** obtained for all 15 benchmark instances
- ⚡ Branch-and-Cut significantly outperformed standard B&B on tight time-window instances
- 🔄 Dantzig-Wolfe decomposition in progress for large-scale scalability (50+ nodes)

---

## 🧠 Concepts Covered

`Operations Research` · `Combinatorial Optimization` · `Integer Programming` · `Graph Theory` · `Scheduling` · `Supply Chain` · `Exact Methods`

---

## 👤 Author

**Dhruv Kumar Sahu**
M.Tech, Industrial & Management Engineering — IIT Kanpur
GATE 2024 AIR 33 | [LinkedIn](https://linkedin.com/in/dhruv-kumar-sahu) · [GitHub](https://github.com/dhruvkumar)

---

## 📄 License
MIT License — feel free to use and build upon this work with attribution.
