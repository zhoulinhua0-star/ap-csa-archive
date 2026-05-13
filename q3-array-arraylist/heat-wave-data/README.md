# Heat-wave-data

## Core Concept

- **`cleanData(double lower, double upper)`**: Walk **`temperatures`** (an **`ArrayList<Double>`**) with index **`i`**. If **`get(i)`** is **below **`lower`** or above **`upper`**, **`remove`** that entry. Removing **during** a **forward `for`** loop shrinks indices after **`i`**; the usual fix is **`i--`** after **`remove`** (or iterate **backward** / use an iterator)—otherwise some values **skip** unchecked.

- **`longestHeatWave(double threshold)`**: **`count`** how many consecutive days have **`temperatures.get(i) > threshold`**; **`else`** resets **`count`** and updates **`max`** with **`Math.max(max, count)`**. Tracks the **longest run** ending before a cooler day—but if the hottest streak reaches the **end** of the list, you still need **`return Math.max(max, count)`** (or equivalent) after the loop—**`return max`** alone misses a streak still “open” at the last element.

## Time Complexity

- `cleanData(lower, upper)`: **Worst-case Θ(n ^ 2)**, **`n = temperatures.size()`** — **`remove`** can shift **`O(n)`** per removal, repeated up to **O(n)** times with a naive forward loop (still depends on how many outliers exist).

- `longestHeatWave(threshold)`: **O(n)** — one pass over **`temperatures`** with **`ArrayList`** **`get`** at **O(1)** amortized per index.
