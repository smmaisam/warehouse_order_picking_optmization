# 📦 Warehouse Order Picking Optimization

This project simulates and visualizes order picking paths in a warehouse using a graph-based layout. It compares an **unoptimized picking sequence** (random order) with an **optimized path** using the **Nearest Neighbor heuristic**.

---

## 🗺️ Overview

Efficient order picking is crucial in warehouse logistics. This simulation demonstrates how optimization can reduce picker travel distance by:

- Modeling the warehouse as a **2D grid graph** (using NetworkX)
- Avoiding **blocked aisle regions**
- Calculating paths using **Dijkstra’s algorithm**
- Applying the **Nearest Neighbor** heuristic for optimization
- Visualizing picker paths with **Matplotlib**

---

## 📐 Grid Setup

- Each walkable cell in the warehouse is represented as a node.
- Picker can move **horizontally or vertically** (4-directional movement).
- Blocked cells (aisles) are excluded from the graph.
- Nodes are connected only if adjacent and walkable.

---

## ✅ Scenario 1: Unoptimized Path (Random Sequence)

- Picker starts and ends at the **gate** (e.g., `(1,1)`).
- **10 items** are randomly placed in walkable cells.
- Items are picked in a **random order**.
- Path segments between items are calculated using **Dijkstra's algorithm**.

### 🔍 Visualization

- 🟥 Red nodes: Item locations  
- 🟩 Green node: Gate  
- 🔵 Blue path: Picker's route  
- 🔢 Numbers: Picking sequence (random)

---

## 🔄 Scenario 2: Optimized Path (Nearest Neighbor Heuristic)

This scenario uses a **greedy approach** to minimize travel distance:

1. Start from the gate.
2. At each step, select the **nearest unvisited item** using Manhattan distance.
3. Use **Dijkstra's shortest path** for each segment.
4. Repeat until all items are picked, then return to the gate.

### ✔️ Constraints

- No movement through aisles (blocked cells).
- Picker moves **only up/down/left/right**.
- All travel must follow valid walkable paths.

### 📊 Visualization

- 🟥 Red nodes: Item locations  
- 🟩 Green node: Gate  
- 🔵 Blue path: Optimized route  
- 🔢 Numbers: Optimized picking order

---

## 🔧 Features

- ✅ Graph-based warehouse layout
- ✅ Obstacle-aware shortest path calculation
- ✅ Unoptimized and optimized route comparison
- ✅ Fully visualized picker path
- ✅ Customizable grid size and item count

---

## 🧠 Future Work

- Add **TSP algorithms** (e.g., Genetic Algorithm, Simulated Annealing)
- Support **multiple pickers**
- Introduce **dynamic obstacles**
- Add **animation** or real-time simulation
- Calculate **performance metrics** (e.g., total distance, time saved)

---

## 📦 Requirements

Install dependencies:

```bash
pip install networkx matplotlib
