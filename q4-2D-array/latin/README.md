# Latin

## Core Concept

Use for loop to traverse the 2D array: the upper bound for `rowNum` is `arr2D.length` while the upper bound for `colNum` is `arr2D[0].length`.

```java
// Normally we do this in AP CSA
for (int r = 0; r < arr2D.length; r++) {
    for (int c = 0; c < arr2D[0].length; c++) {

    }
}
```

## Time Complexity

- `getColumn(int[][] arr2D, int c)`: **O(n)**, where `n` stands for `arr2D.length`

- `isLatin(int[][] square)`: **O(n * w)**, where `n` is `square.length` and `w` is `square[0].length`, as `getColumn(square, c)` scans `n` rows, assuming `T-dup` and `T-has` is both **O(1)**
