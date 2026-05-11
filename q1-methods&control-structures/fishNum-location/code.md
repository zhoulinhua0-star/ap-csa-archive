```java
// (a)
private int numUnder() {
    int fishNum;
    int numNeeded = (int)(minDensity * theEnv.numRows() * theEnv.numCols()) + 1;
    if (fishNum >= numNeeded) { return 0; }
    return numNeeded - fishNum;
}

// (b)
private Location randomLocation() {
     int randomRow = (int)(Math.random() * theEnv.numRows());
     int randomCol = (int)(Math.random() * theEnv.numCols());
      return new Location(randomRow, randomCol);
}
```