```java
// (a)
private double average(int first, int last) {
    int count = last - first + 1;
    int sum = 0;
   for (int i = first; i <= last; i++) {
      sum += scores[i];
    }
    return (double) sum / count;
}

// (b)
private boolean hasImproved() {
    for (int i = 0; i < scores.length - 1; i++) {
        if (scores[i + 1] < scores[i]) { return false; }
    }
    return true;
}

// (c)
public double finalAverage() {
   if (!hasImproved()) {
      return average(0, scores.length - 1);
    } else {
      return average(scores.length / 2, scores.length - 1);
    }
}
```