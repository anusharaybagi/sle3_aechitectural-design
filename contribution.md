# CONTRIBUTION.md

## Project Contribution

This project focuses on the **BFS vs DFS – Empirical Performance Analysis System** using a 20-node graph from **A to T**. The system compares BFS and DFS using execution time, nodes expanded, and py-spy profiling.

## Contribution Areas

* Implemented the **BFS search algorithm** using a queue.
* Implemented the **DFS search algorithm** using a stack.
* Created the 20-node graph structure from **A to T**.
* Defined the three goal cases:

  * Best Case: A → B
  * Average Case: A → C → G → M
  * Worst Case: A → B → F → L → T
* Counted the number of expanded nodes.
* Measured execution time using `time.perf_counter()`.
* Performed **3 benchmark runs per case**.
* Calculated average execution time in milliseconds.
* Used **py-spy** for performance stack profiling.
* Generated the `profile.svg` flame graph.
* Designed the complete **Full C4 Model** architecture.
* Documented Context, Container, Component, and Code levels.

## Coding Guidelines

* Keep the code simple and readable.
* Use meaningful function and variable names.
* Keep BFS and DFS implementations separate.
* Use a queue for BFS and a stack for DFS.
* Maintain the same graph structure for both algorithms.
* Use `time.perf_counter()` for execution timing.
* Avoid unnecessary changes to the existing implementation.
* Test the program after making changes.

## Testing

The system should be tested for:

1. BFS traversal.
2. DFS traversal.
3. All nodes from A to T.
4. Starting node A.
5. Best Case: A → B.
6. Average Case: A → C → G → M.
7. Worst Case: A → B → F → L → T.
8. Number of nodes expanded.
9. Execution time.
10. Average execution time over 3 runs.
11. py-spy profiling.
12. Generation of `profile.svg`.

## Git Workflow

1. Update the required project files.
2. Test the implementation.
3. Add the changes using Git.
4. Commit the changes with a meaningful message.
5. Push the changes to the repository.

### Example Commit Messages

```text
Added BFS implementation
Added DFS implementation
Added 20-node graph
Added performance benchmarking
Added py-spy profiling
Added Full C4 architecture
Updated project documentation
```

## C4 Architecture Contribution

The project is documented using the **Full C4 Model**:

### Level 1 – Context

Shows the user interacting with the BFS vs DFS empirical performance analysis system.

### Level 2 – Container

Includes:

* Graph Input & Case Configurator
* Search Engine
* BFS Module
* DFS Module
* Performance Profiler
* Output / Results

### Level 3 – Component

The Search Engine contains:

* Frontier
* Visited Set
* Goal Test
* Node Counter & Timer

### Level 4 – Code

The main code elements include:

* `bfs(graph, start, goal)`
* `dfs(graph, start, goal)`
* `graph`
* `profile_search.py`

## Performance Analysis

The system compares BFS and DFS using two main performance measures:

* **Execution time**
* **Number of nodes expanded**

The benchmark runs each case three times using `time.perf_counter()` and records the average execution time.

## Profiling Contribution

The project uses **py-spy** to record performance stack traces and generate a flame graph:

```text
profile.svg
```

The profiling helps visualize the execution behaviour of the search system.

## Design Contribution

The architecture separates:

* Graph definition
* Search algorithm traversal
* Performance timing
* Node expansion counting
* Stack profiling

BFS uses a **FIFO queue**, while DFS uses a **LIFO stack**, making their traversal behaviour and performance differences clear.

## AI Contribution

AI tools were used to:

* Structure the Full C4 Model documentation.
* Format Context, Container, Component, and Code levels.
* Prepare Mermaid diagram representations for draw.io.

The **program implementation, benchmarking execution, node counting, and py-spy profile generation were conducted by the student**.

## Conclusion

The contribution provides a complete architectural design and empirical performance analysis of BFS and DFS. The Full C4 Model connects the system context with the specific functions in `profile_search.py` and shows how queue-based and stack-based traversal affect node expansion and execution runtime.
