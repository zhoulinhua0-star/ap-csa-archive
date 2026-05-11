# LightBoard

## Core Concept

### Initialize the array first

Do not forget to initilize the array first in the method properly by:

```java
lights = new boolean[numRows][numCols];
```

### Possibility

**How to deal with possibilities in AP CSA:** Use Math.random() < `certain double value`

Think of that inequality as a **probability gate**: pick a **threshold** `p` between **0.0** and **1.0**. 

Details that often show up on FRQs:

- **`Math.random()`** returns a **double** in the range **0.0 (inclusive) up to but not including 1.0** — so it is **≥ 0.0** and **always strictly less than 1.0**.

- Each call is **independent**: every **`Math.random()`** is a **new** draw, so in a nested loop each **`lights[r][c]`** gets its **own** random outcome.

e.g. less than 40%:

```java
if (Math.random() < 0.4) {
    lights[r][c] = true;
} else {
    lights[r][c] = false;
}
```

# Time complexity

- `LightBoard(int numRows, int numCols)`: **O(n * m)** , where `n` is `numRows` and `m` is `numCols`

- `evaluateLight(int row, int col)`: **O(n)**
