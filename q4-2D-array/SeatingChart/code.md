```java
SeatingChart(Name[] names, int rows, int cols) {
    chart = new String[rows][cols];
    
    for (int r = 0; r < rows; r++) {
        for (int c = 0; c < cols; c++) {
            chart[r][c] = "";
        }
    }

    for (Name n: names) {
        String formatted = n.lastName + n.firstName;
        
        int r = (int) (Math.random() * rows);
        int c = (int) (Math.random() * cols);

        while (!chart[r][c].isEmpty()) {
            int r = (int) (Math.random() * rows);
            int c = (int) (Math.random() * cols);
        }
        
        chart[r][c] = formatted;
    }
}
```