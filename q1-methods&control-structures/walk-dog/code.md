```java
// (a)
public int walkDogs(int hour) {

    if (company.numAvailableDogs(hour) <= maxDogs) {
        company.updateDogs(hour, numAvailableDogs(hour));
    } else {
        company.updateDogs(hour, maxDogs);
    }

    return Math.min(company.numAvailableDogs(hour), maxDogs);
}

// (b)
public int dogWalkShift(int startHour, int endHour) {
    int pay = 0;
    for (int h = startHour; h <= endHour; h++) {
        pay += 5 * walkDogs(h);

        boolean isPeak = h >= 9 && h <= 17;
        boolean isMax = walkDogs(h) == maxDogs;
        if (isPeak || isMax) { pay += 3; }
    }
    return pay;
}
```