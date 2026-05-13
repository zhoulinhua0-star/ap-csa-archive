# Candy-flavor-box

## Core Concept

- **`moveCandyToFirstRow(int col)`**: If **`box[0][col]`** is already nonempty, nothing moves—return **true**. Otherwise walk down column **`col`** from row **1** to **`box.length - 1`**; take the **first** non-**`null`** **`Candy`** and **move** it to **`box[0][col]`**, set the source cell to **`null`**, return **true**. If no candy appears in that column below the top, return **false**. The snippet writes **`box[0][i]`** when promoting upward; the destination should use column **`col`**: **`box[0][col]`**.

- **`removeNextByFlavor(String flavor)`**: Double-loop over **`box`** in whatever order the task specifies (**usually** row/column traversal from the requested corner). Pick the **first** cell with a non-**`null`** **`Candy`** whose **`getFlavor()`** **`equals(flavor)`**; **remove** it from the grid. Store the reference first (**e.g.** `Candy c = box[r][c]; box[r][c] = null; return c`), because nulling the cell and then **`return box[r][c]`** returns **`null`**. Row/column limits are normally **`rows = box.length`** and **`cols = box[0].length`**—swapping those dimensions for **`r`** and **`c`** only holds when **`rows == cols`** (square grid).

## Time Complexity

- `moveCandyToFirstRow(int col)`: **O(R)** in the worst case, **`R = box.length`**—one downward pass in a single column.

- `removeNextByFlavor(String flavor)`: **O(R * C)** in the worst case, **`R = box.length`**, **`C = box[0].length`**—nested grid scan (plus **`String`** **`equals`** on flavor names).
