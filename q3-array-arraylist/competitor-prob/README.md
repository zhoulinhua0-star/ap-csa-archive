# Competitor-prob

## Core Concept

- **`Round(String[] names)`**: Build **`competitorList`** as a new **`ArrayList<Competitor>`**. Loop **`i`** from **`0`** to **`names.length - 1`**, and **`add`** a **`Competitor`** for each name, using **`names[i]`** and seed / order **`i + 1`** (so numbering starts at **1**).

- **`buildMatches()`**: Build a fresh **`ArrayList<Match>`**. Branch on whether **`competitorList.size()`** is **even** or **odd**:
  - **Even**: For **`i`** from **`0`** up to **`size/2 - 1`**, create a **`Match`** between **`competitorList.get(i)`** and **`competitorList.get(size - 1 - i)`** (pair first vs last, then move inward), and **`add`** each match to the result list.
  - **Odd**: Loop while **`i < competitorList.size() / 2 + 1`**, pairing **`get(i)`** with **`get(competitorList.size() - i)`**, and **`add`** each **`Match`**. (Same “ends toward the middle” idea as the even case, with a longer loop; **`get(size - i)`** is **out of range** when **`i == 0`** unless the code uses **`size - 1 - i`** or similar—worth double-checking against the problem spec.)

## Time Complexity

- `Round(String[] names)`: **O(n)**, where `n` is `names.length`

- `buildMatches()`: **O(m)** where **`m`** is **`competitorList.size()`** — about **`m / 2`** iterations, **`ArrayList` `get`** and **`add`** treated as **O(1)** amortized.
