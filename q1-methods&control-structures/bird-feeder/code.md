```java
// (a)
public void simulateOneDay(int numBirds) {
    int consumed = (int) (Math.random() * 41) + 10; 
    
    boolean isNormal = Math.random() < 0.95;
    
    if (isNormal && numBirds * consumed <= currentFood) {
        currentFood -= numBirds * consumed;
    } else {
        currentFood = 0;
    }
} 

// (b)
public int simulateManyDays(int numBirds, int numDays) {
    for (int day = 0; day < numDays; day++) {
        if (currentFood == 0) {
            return day;
        }
        simulateOneDay(numBirds);
    }
    return numDays;
}
```
