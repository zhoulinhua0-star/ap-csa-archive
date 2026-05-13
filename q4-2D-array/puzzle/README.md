# Puzzle

## Core Concept

- **`SumOrSameGame(int numRows, int numCols)`**: Allocate **`puzzle`** as a 2D **`int`** array with the given dimensions. Use **nested loops** so every cell gets a random integer from **1** through **9** via **`(int) (Math.random() * 9) + 1`**.

- **`clearPair(int row, int col)`**: Read **`val`** from **`puzzle[row][col]`**. Scan with **`r`** from **`row`** through **`numRows - 1`** and **`c`** from **`0`** through **`numCols - 1`**. Ignore the starting coordinate using **`r != row || c != col`**. For another cell **`puzzle[r][c]`** such that **`puzzle[r][c] == val`** OR **`puzzle[r][c] + val == 10`**, set **`puzzle[r][c]`** to **`0`** and **`return true`** (first match wins). If the loops finish with no hit, **`return false`**. (Relies on **`puzzle`**, **`numRows`**, and **`numCols`** from the class.)

## Time Complexity

- `SumOrSameGame(int numRows, int numCols)`: **O(R * C)** where **`R = numRows`** and **`C = numCols`** — one assignment per cell.

- `clearPair(int row, int col)`: **O((R − row) * C)** in the worst case (**`R`** and **`C`** as above): nested loops cover the rectangle from **`row`** through the bottom row and all columns. **O(R * C)** if you simplify to grid size bounds.
