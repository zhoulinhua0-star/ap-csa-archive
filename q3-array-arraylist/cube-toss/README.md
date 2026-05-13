# Cube-toss

## Core Concept

```java
return (maxRun > 1) ? maxIdx : -1;
```

is equivalent to: 

```java
if (maxRun > 1) {
    return maxIdx;
} else  {
    return -1;
}
```

## Time Complexity

- `getCubeTosses(NumberCube cube, int numTosses)`: **O(n)**, where `n` is `numTosses`   

- `getLongestRun(int[] values)`: **O(m)**, where `m` is `values.length`