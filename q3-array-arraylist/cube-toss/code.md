```java
// (a)
public static int[] getCubeTosses(NumberCube cube, int numTosses) {
    int[] arr = new int[numTosses];
    for (int i = 0; i < numTosses; i++) {
        arr[i] = cube.toss();
    }
    return arr;
}

// (b)
public static int getLongestRun(int[] values) {
    int maxIdx = -1;
    int maxRun = 1;

    int currentIdx = 0;
    int currentRun = 1;

    for (int i = 0; i < values.length - 1; i++) {
        if (values[i] == values[i + 1]) {
            currentRun++;
     } else {
            if (maxRun < currentRun) {
                  maxRun = currentRun; 
                  maxIdx = currentIdx;
            }
            currentIdx = i + 1;
            currentRun = 1;
    }
    
    if (maxRun < currentRun) {
        maxRun = currentRun;
        maxIdx = currentIdx;
    }

    }
    return (maxRun > 1) ? maxIdx : -1;
}
```