# Pacman AI: Search Algorithms (CS188)

Implementation of classic search algorithms, heuristic optimization, and theoretical problem formulations based on UC Berkeley's **CS188: Introduction to Artificial Intelligence**[cite: 8, 11].

---

##  Project Overview

This project consists of two main parts:
1. **Pacman Search Problem (Q1 – Q8):** Implementation of uninformed/informed search algorithms and heuristics to navigate mazes and collect food efficiently[cite: 11].
2. **Theoretical Foundations:** Search space modeling, iterative deepening properties, heuristic admissibility/consistency, and pancake sorting bounds[cite: 10].

---

##  Practical Implementations (`search.py` & `searchAgents.py`)

### 1. Core Graph Search Algorithms (`search.py`)
* **Q1: Depth-First Search (DFS)** — Graph search using LIFO frontier (Stack)[cite: 11, 12]. Avoids cycles via an explicit visited list[cite: 11, 12].
* **Q2: Breadth-First Search (BFS)** — FIFO queue implementation ensuring shortest path in unweighted graphs[cite: 11, 12].
* **Q3: Uniform Cost Search (UCS)** — Priority queue frontier expanding lowest cumulative path cost first[cite: 11, 12]. Includes a custom update method (`difupdate`) for state-level cost relaxation[cite: 11, 12].
* **Q4: A* Search** — Best-first search balancing backward cost $g(n)$ and forward heuristic estimate $h(n)$ ($f(n) = g(n) + h(n)$)[cite: 11, 12].

### 2. Search Problems & Domain Heuristics (`searchAgents.py`)
* **Q5: Corners Problem** — State modeling tracking `(current_position, visited_corners_list)`[cite: 11, 13]. Goal is reached when all four corners are visited[cite: 11, 13].
* **Q6: Corners Heuristic** — Consistent and admissible heuristic computing the sum of minimum Manhattan distances across unvisited corners[cite: 11, 13].
* **Q7: Food Search Problem (All Dots)** — Heuristic estimating remaining cost based on maximum Manhattan distance to remaining food dots[cite: 11, 13].
* **Q8: Suboptimal Search (Closest Dot)** — Greedy approach using BFS iterations to find the nearest food pellet successively[cite: 11, 13].

---

##  Theoretical Analysis Summary

* **Iterative Deepening Search (IDS):** Analysis of node expansion count in finite search trees with branching factor $b$ and depth $d$ ($\sum_{i=0}^d (d - i + 1)b^i$)[cite: 10].
* **Fringe Exploration Order:** Comparative tracing of DFS, BFS, IDS, Greedy Best-First, and A* exploration paths[cite: 10].
* **Pancake Sorting as a Search Problem:** Mathematical induction proving $n \le f(n) \le 2n$ for $n \ge 4$, with a state space size of $n!$ configurations[cite: 10].
* **Multi-Agent Grid Navigation:** Search space formulation ($n^{2k}$) and Manhattan distance heuristics for multi-agent coordinated goal reachability[cite: 10].

---

##  Repository Structure
.
├── search.py          # DFS, BFS, UCS, and A* implementations
├── searchAgents.py    # Search problems (Corners, Food) & heuristics
└── README.md          # Project documentation
