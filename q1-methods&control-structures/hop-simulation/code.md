```java
// (a)
public boolean simulate() {
    int pos = 0;
    for (int i = 0; i < maxHops; i++) {
        pos += hopDistance();
        if (pos < 0) { 
            return false; 
        } else if (pos >= goalDistance) {
            return true;
        }
    }
    return false;
}

// (b)
public double runSimulations(int num) {
    int count = 0;
    for (int i = 0; i < num; i++) {
        if (simulate()) { count++; }
    }
    return (double) count / num;
}
```