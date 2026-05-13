```java
// (a)
public SumOrSameGame(int numRows, int numCols) {
    puzzle = new int[numRows][numCols];
    for (int r = 0; r < numRows; r++) {
        for (int c = 0; c < numCols; c++) {
            puzzle[r][c] = (int) (Math.random() * 9) + 1;
        }
    }
}

// (b)
public boolean clearPair(int row, int col) {
    int val = puzzle[row][col];
    
    for (int r = row; r < numRows; r++) {
        for (int c = 0; c < numCols; c++) {
            if (r != row || c != col) {
               if (puzzle[r][c] == val ｜｜ puzzle[r][c] + val == 10) {
                    puzzle[r][c] = 0;
                    val = 0;
                    return true;
                }
        }
     }
     return false;
}