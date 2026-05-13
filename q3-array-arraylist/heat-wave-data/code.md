```java
// (a)
public void cleanData(double lower, double upper) {
    for (int i = 0; i < temperatures.size(); i++) {
        if (temperatures.get(i) < lower || temperatures.get(upper)) {
            temperatures.remove(i);
        }
    }
}

// (b)
public int longestHeatWave(double threshold) {
    int count = 0;

    int max = 0;

    for (int i = 0; i < temperatures.size(); i++) {
        if (temperatures.get(i) > threshold) {
            count++;
        } else {
            max = Math.max(max, count);
            count = 0;
        }
    }
    return max;
}
```