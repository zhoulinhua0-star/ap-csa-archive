```java
// (a)
public Location getNextLoc(int row, int col) {
    boolean hasRight = col <= grid[0].length - 2;
    boolean hasBelow = row <= grid.length - 2;

    if (hasRight && hasBelow) {
        int right = grid[row][col + 1];
        int below = grid[row + 1][col];
        if (right < below) {
            return new Location(row, col + 1);
        } else {
            return new Location(row + 1, col);
        }
    } else if (hasRight && !hasBelow) {
        return new Location(row, col + 1);
    } else if (!hasRight && hasBelow) {
        return new Location(row + 1, col);
    }
    return null;
}

// (b)
public int sumPath(int row, int col) {
    int sum = grid[row][col];

    Location next = getNextLoc(row, col);
    while (next != null) {
        row = next.getRow();
        col = next.getCol();
        sum += grid[row][col];
        next = getNextLoc(row, col);
    }
    return sum;
}
```
