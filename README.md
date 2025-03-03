# Pacman AI Search Algorithms

## Overview

This repository contains my implementation of various search algorithms for the classic Pacman game as part of my **CSCE 580: Artificial Intelligence** course at the **University of South Carolina**. The goal of this assignment is to develop intelligent agents capable of navigating Pacman's world efficiently by implementing and testing different search strategies.

## Getting Started

To get started, first download and unzip the provided code (`search.zip`). Then, navigate to the extracted directory and run the Pacman game with the following command:

```sh
python pacman.py
```

Pacman lives in a maze, searching for food while avoiding obstacles. This assignment involves implementing various search algorithms to improve Pacman’s ability to navigate efficiently.

## Implemented Search Algorithms

I have implemented the following search algorithms in `search.py`:

### 1. Depth-First Search (DFS)

Implemented in `depthFirstSearch` function.

```sh
python pacman.py -l tinyMaze -p SearchAgent
python pacman.py -l mediumMaze -p SearchAgent
python pacman.py -l bigMaze -z .5 -p SearchAgent
```

DFS explores the deepest nodes first using a **stack** data structure. However, it does not guarantee the shortest path.

### 2. Breadth-First Search (BFS)

Implemented in `breadthFirstSearch` function.

```sh
python pacman.py -l mediumMaze -p SearchAgent -a fn=bfs
python pacman.py -l bigMaze -p SearchAgent -a fn=bfs -z .5
```

BFS explores nodes level by level using a **queue** data structure and guarantees the shortest path.

### 3. Uniform Cost Search (UCS)

Implemented in `uniformCostSearch` function.

```sh
python pacman.py -l mediumMaze -p SearchAgent -a fn=ucs
python pacman.py -l mediumDottedMaze -p StayEastSearchAgent
python pacman.py -l mediumScaryMaze -p StayWestSearchAgent
```

UCS finds the optimal path by considering the **cost of each move**.

### 4. A\* Search (A\*)

Implemented in `aStarSearch` function.

```sh
python pacman.py -l bigMaze -z .5 -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic
```

A\* uses a **heuristic function** (e.g., Manhattan distance) to optimize the search process.

### 5. Corners Problem & Heuristics

Implemented `CornersProblem` and `cornersHeuristic`.

```sh
python pacman.py -l tinyCorners -p SearchAgent -a fn=bfs,prob=CornersProblem
python pacman.py -l mediumCorners -p SearchAgent -a fn=bfs,prob=CornersProblem
python pacman.py -l mediumCorners -p AStarCornersAgent -z 0.5
```

Developed an admissible and consistent heuristic to efficiently solve the problem of visiting all four corners.

### 6. Food Search Problem

Implemented `foodHeuristic` for A\* search.

```sh
python pacman.py -l trickySearch -p AStarFoodSearchAgent
```

Optimized Pacman's ability to eat all food pellets while minimizing path cost.

### 7. Suboptimal Search (Greedy Closest Dot Search)

Implemented `findPathToClosestDot` function.

```sh
python pacman.py -l bigSearch -p ClosestDotSearchAgent -z .5
```

This agent greedily finds and consumes the nearest food dot, sacrificing optimality for speed.

## Running Help Command

To view all available commands and options, use:

```sh
python pacman.py -h
```

## Notes

- If you encounter errors related to Tkinter, refer to the installation guide for your OS.
- Commands for running different parts of the project are listed in `commands.txt` for easy execution.

## Conclusion

This project provided hands-on experience with fundamental search algorithms in AI. By implementing and comparing DFS, BFS, UCS, and A\*, I gained a deeper understanding of how different strategies affect problem-solving efficiency. Additionally, designing heuristics for A\* reinforced the importance of admissibility and consistency in search problems.

---

### Course: CSCE 580 - Artificial Intelligence

### Instructor: Pooyan Jamshidi

### Student: Ryan Caudill

