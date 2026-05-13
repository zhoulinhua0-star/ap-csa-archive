```java
// (a)
TravelPlan(String destination) {
    this.destination = destination;
    plans = new ArrayList<Tour>();
}

// (b)
public boolean addTour(Tour t) {
    if (!checkForConflicts(t)) {
        plans.add(t);
        return true;
    } else {
        return false;
    }
}
```