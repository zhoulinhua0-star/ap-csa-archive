# Roll-die

## Core Concept

- Use `Math.random()` to form integers between given numbers:

e.g.

```java
// Generate integers between 1 and `numFaces`
int random = (int) (Math.random() * numFaces) + 1;
```

- for loop

- do not forget to add things like `(double)` or `(int)` before the variable if needed

## Time Complexity

- `roll()`: **O(1)**

- `runSimulation()`: **O(n)**, where `n` is `numSampleSize`