# SeatingChart

## Core Concept

- Use a **2D `String` array** (`rows` × `cols`) as the seating chart.

- **Nested `for` loops** set every cell to `""` so you can distinguish “empty” from “occupied.”

- For each **`Name`**, build the displayed string as **`lastName + firstName`**.

- Pick a random row and column with **`(int) (Math.random() * rows)`** and **`(int) (Math.random() * cols)`**, then use a **`while`** loop to **retry** until the chosen cell is still empty (`!chart[r][c].isEmpty()` is false), then store the formatted name there.

## Time Complexity

- `SeatingChart(Name[] names, int rows, int cols)`:

  - **O(rows * cols)** for allocating and initializing the grid with empty strings.

  - **O(n)** passes over **`names`** where **`n`** is **`names.length`**; each pass does random index generation and assignment. If two random picks collide with an already-filled seat, the **`while`** loop runs again, so cost per name grows with contention. **Worst case** (almost every seat taken) can approach **O(n * rows * cols)** retries before finding a spot, assuming a seat eventually opens.
