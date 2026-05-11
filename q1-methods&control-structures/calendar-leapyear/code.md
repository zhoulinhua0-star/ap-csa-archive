```java
// (a)
public static int numberOfLeapYears(int year1, int year2) {
    int count = 0;
    for (int year = year1; year <= year2; year++) {
        if (isLeapYear(year)) { count++; }
    }
    return count;
}

// (b)
public static int dayOfWeek(int month, int day, int year) {
    int dayCount = dayOfYear(month, day, year);
    return (firstDayOfYear(year) + dayCount - 1) % 7;
}
```