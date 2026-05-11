# StepTracker

## Core Concept

- additional instance variables needed in this specific case, like

 ```java
private int totalSteps;
private int numDays;
private int numActiveDays;
```

- never forget to think about the edge cases, particularly like

```java
if (numDays == 0) { return 0.0; }
return (double) totalSteps / numDays;
```

Reminder: `0.0` is a `double` type, `(double) 0` is a `double` type, while `0` itself is an `int` type.

# Time Complexity

- **O(1)**