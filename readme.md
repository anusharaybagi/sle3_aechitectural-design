# BFS vs DFS – Empirical Performance Analysis System

## Project Overview

The **BFS vs DFS – Empirical Performance Analysis System** evaluates and compares the actual performance of **Breadth-First Search (BFS)** and **Depth-First Search (DFS)** on a **20-node graph from A to T**, starting from node A.

The system measures:

* Execution time using `time.perf_counter()`
* Number of expanded nodes
* Average execution time over 3 runs
* Performance stack traces using py-spy
* Flame graph output using `profile.svg`

The system architecture is documented using the **Full C4 Model**: Context, Container, Component, and Code.

---

## Objectives

1. Implement BFS and DFS search algorithms.
2. Use a 20-node graph from A to T.
3. Compare BFS and DFS performance.
4. Count the number of expanded nodes.
5. Measure execution time using `time.perf_counter()`.
6. Run each test case 3 times.
7. Calculate average execution time.
8. Use py-spy for stack profiling.
9. Generate the `profile.svg` flame graph.
10. Represent the architecture using the Full C4 Model.

---

## Graph and Test Cases

The system starts searching from node **A**.

### Best Case

```text
A → B
```

### Average Case

```text
A → C → G → M
```

### Worst Case

```text
A → B → F → L → T
```

The graph contains nodes from **A to T**.

---

# Full C4 Model

## Level 1 – Context Diagram

The Context level shows the interaction between the **user** and the BFS vs DFS performance analysis system.

The user triggers the search on the 20-node A–T graph.

The system returns:

* Execution timing
* Node expansion count
* py-spy flame graph

---

## Level 2 – Container Diagram

The system contains the following containers:

### 1. Graph Input & Case Configurator

Stores the 20-node graph topology and defines the Best, Average, and Worst test cases.

### 2. Search Engine

Controls the execution flow and invokes the search algorithms.

### 3. BFS Module

Performs Breadth-First Search using a queue and explores nodes level by level.

### 4. DFS Module

Performs Depth-First Search using a stack and explores deep branches.

### 5. Performance Profiler

Uses `time.perf_counter()` for timing and py-spy for stack profiling.

### 6. Output / Results

Displays:

* Average execution time
* Nodes expanded
* `profile.svg`

---

## Level 3 – Component Diagram

The Search Engine consists of four components:

### Frontier

Stores undiscovered frontier nodes.

* BFS → `collections.deque` queue
* DFS → list stack

### Visited Set

Keeps track of visited nodes and prevents cyclic loops.

### Goal Test

Checks whether the current node reaches the target goal.

### Node Counter & Timer

Counts expanded nodes and measures execution time using `time.perf_counter()`.

---

## Level 4 – Code Level

The main code elements are:

```text
bfs(graph, start, goal)
dfs(graph, start, goal)
graph
profile_search.py
```

* `bfs()` performs level-by-level search.
* `dfs()` performs deep-branch search.
* `graph` stores the 20-node adjacency structure.
* `profile_search.py` runs the benchmark 3 times per case and uses `time.perf_counter()`.

---

## Performance Measurement

The system uses:

```python
time.perf_counter()
```

to measure execution time.

Each test case is executed **3 times**, and the average execution time is calculated.

The system also counts the number of nodes expanded to evaluate the algorithmic effort.

---

## Py-Spy Profiling

The system uses **py-spy** to record performance stack traces.

Example command:

```bash
py-spy record -o profile.svg -- python profile_search.py
```

The profiling output is:

```text
profile.svg
```

This provides a flame graph visualizing the program's stack activity.

---

## Design Decisions

* The graph is represented using standard Python dictionaries and functions.
* BFS and DFS are kept separate to show the difference between **FIFO queue** and **LIFO stack**.
* `time.perf_counter()` is used for high-precision timing.
* Node expansion counting is used along with execution time.
* The architecture separates graph definition, algorithm traversal, timing, and stack profiling.

---

## AI Contribution

AI was used to help:

* Structure the Full C4 Model documentation.
* Format the Context, Container, Component, and Code levels.
* Prepare Mermaid diagram representations for draw.io.

The program implementation, benchmarking execution, node counting, and py-spy profile generation were conducted by the student.

---

## Conclusion

The Full C4 Model provides a clear architectural view of the BFS vs DFS empirical profiling system.

It connects the overall system context to the specific functions in `profile_search.py` and makes the effect of **queue-based BFS and stack-based DFS** on node expansion and execution runtime clear.
