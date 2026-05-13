```java
// (a)
public int findFreeBlock(int period, int duration) {
    int count = 0;
    for (int minute = 0; minute <= 59; i++) {
        if (isMinuteFree(period, minute)) {
            count++;
            if (count == duration) {
                return minute - count + 1;
            }
        } else {
            count = 0;
        }
    }
    return -1;
}

// (b)
public boolean makeAppointment(int startPeriod, int endPeriod, int duration) {
    for (int i = startPeriod; i <= endPeriod; i++) {
        int minute = findFreeBlock(period, duration);
        if (minute != -1) {
            reserveBlock(i, minute, duration);
            return true;
        }
    }
    return false;
}
```