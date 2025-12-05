# PATHFINDING ALGORITHMS

**Language:** Java  
**README Language:** English

---

## ⭐ Project Summary
This project implements two classical heuristic search algorithms used in Artificial Intelligence and Robotics: **A\*** and **Best-First Search**.  
The goal is to provide a clear, modular, and educational implementation of pathfinding on grid-based maps, demonstrating how informed search works and how heuristics influence performance.

It is designed as a compact academic project where the focus is on:
- understanding how search trees are expanded,
- comparing different heuristics,
- analyzing optimality vs. speed,
- and learning how to structure reusable search components in Java.

### What this project teaches
By completing and studying this project, one develops skills in:

#### Artificial Intelligence
- Heuristic search  
- Evaluation functions (f, g, h)  
- Optimality conditions (heuristic admissibility and consistency)  
- Tradeoffs between A* and greedy strategies  

#### Algorithms & Data Structures
- Priority queues and node ordering  
- Graph exploration  
- State representation  
- Parent tracking and path reconstruction  

#### Java Programming
- Interfaces and abstraction (`Heuristic`, `Search`)  
- Object-oriented design in algorithmic contexts  
- Clean separation of model (Map, State) and logic (Search algorithms)

---

## 🧩 Technologies & Tools Used
- **Java (JDK 11+)** – main programming language  
- **PriorityQueue** – for frontier management  
- **Object-Oriented Programming** – to structure search algorithms and heuristics  
- **Plain text maps** – lightweight custom format for grid environments  
- **No external libraries** – everything implemented from scratch for educational clarity

---

## 📁 File Structure
```
AStar.java        → Implementation of the A* search algorithm
BestFirst.java    → Implementation of Greedy Best-First Search
Heuristic.java    → Interface for heuristic functions
Heuristics.java   → Predefined heuristic functions (Manhattan, Euclidean, etc.)
Main.java         → Program entry point; runs searches and prints results
Map.java          → Loads and represents a grid map
Search.java       → Abstract class shared by all search strategies
State.java        → Node representation: position, costs, and parent state
```

### Design Philosophy
- **Separation of concerns:**  
  - `Map` knows the environment  
  - `State` knows its position and cost  
  - `Search` defines the general algorithm flow  
  - `AStar` and `BestFirst` override the evaluation strategy  

- **Extendability:**  
  Adding a new heuristic or search algorithm requires only adding a new class that implements one of the existing interfaces.

---

## 🔍 How the Algorithms Work

### A* Search
A* combines:
- `g(n)` = cost from the start  
- `h(n)` = heuristic estimate to the goal  

Evaluation function:
```
f(n) = g(n) + h(n)
```

A* is:
- **Complete**  
- **Optimal** (when h is admissible)  
- **Efficient** for many grid navigation tasks  

---

### Best-First Search
Best-First explores nodes that appear closest to the goal:
```
f(n) = h(n)
```

It is:
- Very fast  
- Not optimal  
- Greedy and may explore unnecessary detours  

---

## 🎯 Heuristics
The project includes several heuristics via `Heuristics.java`, such as:
- Manhattan Distance  
- Euclidean Distance  
- Diagonal / Chebyshev Distance  

Heuristics can be swapped with a single line of code, enabling easy experimentation.

---

## 🗺️ Map Format
Typical layout:
```
.  → free cell
#  → obstacle
S  → start
G  → goal
```

Example:
```
########
#S.....#
#..##..#
#...G..#
########
```

Maps are internally processed by `Map.java`.

---

## 🏗️ Requirements
- Java 11+  
- Terminal or IDE  
- No external dependencies

---

## ▶️ How to Build & Run

### 1. Compile
```
javac *.java
```

### 2. Run
Depending on your `Main.java`:

```
java Main path/to/map.txt startX startY goalX goalY
```

or simply:

```
java Main
```

---

## ✔️ Summary
This project is a clean, modular, and educational implementation of classical pathfinding techniques using heuristic search.  
It demonstrates essential AI concepts, algorithm design principles, and professional Java structuring without relying on any external frameworks.
