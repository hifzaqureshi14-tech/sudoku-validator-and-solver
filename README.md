# Sudoku Solver and Validator in Python

## Overview

This project implements a basic Sudoku validator and solver using Python. It is designed to demonstrate how a classic constraint-based problem can be handled programmatically with simple logic and recursion. The program first verifies whether a given Sudoku grid is valid, and then attempts to solve it using a backtracking strategy.

---

## Approach

### Validation Logic (`checkboard`)

The validation function checks whether the current state of the board follows Sudoku rules. It performs three independent checks:

* **Row check:** Ensures that each row contains unique values (excluding empty cells).
* **Column check:** Ensures that each column contains unique values.
* **Subgrid check:** Verifies each 3×3 box for duplicate values.

Empty cells are represented by `"."` and are ignored during these checks.

---

### Solving Strategy (`solver`)

The solver uses a recursive backtracking technique:

* It scans the grid to locate an empty cell.
* For that cell, it tries values from 1 to 9.
* After placing a value, the board is validated.
* If valid, the solver proceeds recursively to fill the next cell.
* If a conflict occurs later, the algorithm reverts the change (backtracks) and tries the next value.

This process continues until the grid is completely filled or no valid configuration can be found.

---

## Code Layout

```id="c1a9ks"
checkboard(board)   # Handles validation of the Sudoku grid
solver(board)       # Applies backtracking to solve the puzzle
main block          # Initializes the board and runs validation + solver
```

---

## Sample Input

The following board is used as an example:

```id="y7n2qp"
5 3 . | . 7 . | . . .
6 . . | 1 9 5 | . . .
. 9 8 | . . . | . 6 .
------+-------+------
8 . . | . 6 . | . . 3
4 . . | 8 . 3 | . . 1
7 . . | . 2 . | . . 6
------+-------+------
. 6 . | . . . | 2 8 .
. . . | 4 1 9 | . . 5
. . . | . 8 . | . 7 9
```

---

## Output

When executed, the program first validates the board:

```id="p0r5xt"
BOARD IS VALID
```

It then prints a completed Sudoku grid:

```id="k3lm9v"
['5', '3', '4', '6', '7', '8', '9', '1', '2']
['6', '7', '2', '1', '9', '5', '3', '4', '8']
['1', '9', '8', '3', '4', '2', '5', '6', '7']
['8', '5', '9', '7', '6', '1', '4', '2', '3']
['4', '2', '6', '8', '5', '3', '7', '9', '1']
['7', '1', '3', '9', '2', '4', '8', '5', '6']
['9', '6', '1', '5', '3', '7', '2', '8', '4']
['2', '8', '7', '4', '1', '9', '6', '3', '5']
['3', '4', '5', '2', '8', '6', '1', '7', '9']
```

---

## Limitations

* The implementation runs entirely in the terminal; no graphical interface is provided.
* Performance may degrade for harder puzzles due to the lack of optimization techniques.
* The solver relies on brute-force backtracking without heuristics such as forward checking or variable ordering.
* Input is hardcoded into the script rather than being read dynamically.
* Only one solution is returned, even if multiple solutions exist.

---

## Possible Enhancements

* Introduce a user interface (e.g., using Tkinter) for better usability.
* Improve efficiency with constraint propagation or heuristic-based search.
* Allow users to input custom boards via file or interactive input.
* Extend the solver to detect and display multiple valid solutions.
* Provide more detailed validation feedback.

---

## Summary

Overall, this project illustrates a straightforward implementation of Sudoku validation and solving. While the approach is simple, it effectively highlights how recursive backtracking can be applied to solve structured grid problems.

---
