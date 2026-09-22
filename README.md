# IAI_SLE2

## SLE-2: BFS and DFS with Performance Profiling

This project demonstrates **Breadth First Search (BFS)** and **Depth First Search (DFS)** on a graph represented using a Python adjacency list.

It also includes instructions for profiling the program with **py-spy** and a static SVG graph visualization.

## Project Structure

```text
IAI_SLE2/
├── bfs_dfs.py
├── graph.svg
├── CONTRIBUTION.md
├── README.md
└── profile.svg          # generated after running py-spy
```

## Graph Used

The graph is:

```text
        A
       / \
      B   C
     / \   \
    D   E---F
```

The SVG version is available in **graph.svg**.

## Algorithms

### BFS

BFS uses a queue and visits vertices level by level.

For the graph starting at A:

```text
A -> B -> C -> D -> E -> F
```

### DFS

DFS explores one branch as deeply as possible before backtracking.

For the graph starting at A:

```text
A -> B -> D -> E -> F -> C
```

## Requirements

- Python 3
- py-spy 0.4.2 or compatible version

Check Python:

```powershell
python --version
```

Check py-spy:

```powershell
py-spy --version
```

If py-spy is not installed:

```powershell
python -m pip install py-spy
```

## Run the Program

From the repository folder:

```powershell
python bfs_dfs.py
```

Expected output:

```text
Graph: {'A': ['B', 'C'], 'B': ['A', 'D', 'E'], 'C': ['A', 'F'], 'D': ['B'], 'E': ['B', 'F'], 'F': ['C', 'E']}
BFS: A -> B -> C -> D -> E -> F
DFS: A -> B -> D -> E -> F -> C
```

## py-spy Profiling

### 1. Generate a flamegraph SVG

Run:

```powershell
py-spy record --output profile.svg -- python bfs_dfs.py
```

This creates **profile.svg**. Open it in a browser to inspect the time spent in Python functions.

### 2. View live activity

```powershell
py-spy top -- python bfs_dfs.py
```

### 3. Record for a running Python process

First find the process ID, then:

```powershell
py-spy record --pid <PID> --output profile.svg
```

Use only a process that you own or are authorized to profile.

## Complexity

For an adjacency-list graph:

| Algorithm | Time | Space |
|---|---|---|
| BFS | O(V + E) | O(V) |
| DFS | O(V + E) | O(V) |

Where:
- **V** = number of vertices
- **E** = number of edges

## Files

- **bfs_dfs.py** - BFS and DFS implementation.
- **graph.svg** - graph visualization.
- **CONTRIBUTION.md** - contribution/AI assistance log.
- **profile.svg** - generated py-spy performance profile.

## Git Commands

After generating or changing files:

```powershell
git status
git add .
git commit -m "Add BFS DFS py-spy profiling and graph"
git push origin main
```

If the remote repository contains newer commits, use:

```powershell
git pull --rebase origin main
git push origin main
```

## Author

Rutuja Patil
