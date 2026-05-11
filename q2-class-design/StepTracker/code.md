```java
public class StepTracker {
    private int minNum;
    private int totalSteps;
    private int numDays;
    private int numActiveDays;

    public StepTracker(int num) {
        minNum = num;
        totalSteps = 0;
        numDays = 0;
        numActiveDays = 0;
    }

    public void addDailySteps(int numOfSteps) {
        totalSteps += numOfSteps;
        numDays++;
        if (numOfSteps >= minNum) {
            this.numActiveDays++;
        }
    }
    
    public int activeDays() {
        return numActiveDays;
    }

    public double averageSteps() {
        if (numDays == 0) { return 0.0; }
        return (double) totalSteps / numDays;
    }
}
```