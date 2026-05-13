```java
// (a)
public boolean isLevelTrailSegment(int start, int end) {
    int max, min = markers[start];
    for (int i = start; i < end; i++) {
        max = Math.max(max, markers[i]);
        min = Math.min(min, markers[i]);
    }
    return max - min <= 10;
}

// (b)
public boolean isDifficult() {
    int count = 0;
    for (int i = 0; i < markers.length - 1; i++) {
        if (Math.abs(markers[i + 1] - markers[i]) >= 30) {
            count++;
        }
    }
    return count >= 3;
}
```