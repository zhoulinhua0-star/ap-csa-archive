```java
// (a)
public int roll() {
    return (int) (Math.random() * this.numFaces) + 1;
}

// (b)
public int runSimulation() {
    int count = 0;

    int die1, die2;
    for (int i = 0; i < this.numSampleSize; i++) {
        die1 = roll();
        die2 = roll();
        if (die1 == die2) { count++; }
    }
    return (int) ((double) count / this.numSampleSize * 100);
}
```