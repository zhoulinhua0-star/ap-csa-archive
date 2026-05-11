```java
// (a)
public LightBoard(int numRows, int numCols) {
    lights = new boolean[numRows][numCols];

    for (int r = 0; r < numRows; r++) {
        for (int c = 0; c < numCols; c++) {
            if (Math.random() < 0.4) {
                lights[r][c] = true;
            } else {
                lights[r][c] = false;
        }
    }
}

// (b)
public boolean evaluateLight(int row, int col) {
    int countIsOn = 0;
    for (int r = 0; r < lights.length; r++) {
        if (lights[r][col]) {
            countIsOn++;
        }
    }

    if (lights[row][col] && countIsOn % 2 == 0) {
        return false;
    }
    
    if (!lights[row][col] && countIsOn % 3 == 0) {
        return true;
    }
     
    return lights[row][col];
}
```