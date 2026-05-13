```java
// (a)
public static boolean isSelfDivisor(int number) {
    int digit = number % 10;
    while (number > 0) {
        if (number % digit != 0 || digit == 0) { return false; }
        number /= 10;
}
    return true;
}

// (b)
public static int[] firstNumSelfDivisors(int start, int num) {
    int[] list = new int[num];
    
    int count = 0;
    int current = start;
    while (count < num) {
        if (isSelfDivisor(current)) {
            list[count] = current;
            count++;
  }
        current++;
}
    return list;
}
```