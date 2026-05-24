# Pathfinding Visualizer

An interactive browser-based tool that visualizes 4 classic pathfinding algorithms step by step on an 18×30 grid.

## Live Demo
Just open `index.html` in any browser — no installation, no server, no dependencies.

## Algorithms Implemented

| Algorithm | Data Structure | Optimal? | Time Complexity |
|-----------|---------------|----------|----------------|
| BFS | Queue (FIFO) | Yes (unweighted) | O(V + E) |
| DFS | Stack (LIFO) | No | O(V + E) |
| Dijkstra | Priority Queue (Min-Heap) | Yes | O((V+E) log V) |
| A* | Priority Queue + Heuristic | Yes (admissible h) | O(E log V) |

## How to Use

1. **Draw walls** — click or drag on the grid
2. **Move start/end** — click "Mode" button to switch between Wall / Start / End
3. **Select algorithm** — click BFS, DFS, Dijkstra, or A*
4. **Run** — click the ▶ Run button
5. **Compare** — click "Clear Path" and run a different algorithm on the same maze

## DSA Concepts Used

- **Graph** — 18×30 grid = implicit graph (540 nodes, ~984 edges)
- **Queue** — BFS traversal (FIFO)
- **Stack** — DFS traversal (LIFO)
- **Priority Queue** — Dijkstra & A* (sorted by cost/f-value)
- **Hash Map** — `prev{}` object for path reconstruction (backtracking)
- **Hash Set** — `visited` Set to prevent revisiting nodes

## Cell Color Legend

| Color | Meaning |
|-------|---------|
| 🟢 Green | Start node |
| 🟠 Orange | End node |
| ⬛ Dark | Wall (blocked) |
| 🟦 Light Blue | Visited (fully explored) |
| 🟩 Teal | Frontier (in queue/stack) |
| 🟡 Gold | Shortest path |

## Project Structure

```
pathfinding-visualizer/
│
├── index.html        ← Complete project (HTML + CSS + JS in one file)
└── README.md         ← This file
```

## Tech Stack

- **HTML5** — Grid structure using CSS Grid
- **CSS3** — Cell state animations and dark navy theme
- **Vanilla JavaScript** — All algorithm logic, no libraries or frameworks

## A* Heuristic

Uses Manhattan Distance (admissible for 4-directional movement):

```
h(n) = |n.row - end.row| + |n.col - end.col|
f(n) = g(n) + h(n)   (total = cost so far + estimated cost to goal)
```

## Key Results

- A* visits ~48% fewer cells than BFS while finding the same optimal path
- DFS is fast but finds longer non-optimal paths
- BFS and Dijkstra behave identically on unweighted grids

## Academic Context

Built as an exam project for the **Data Structures & Algorithms** course, B.Tech Computer Science.

---

*Open `index.html` in your browser to run the visualizer.*
