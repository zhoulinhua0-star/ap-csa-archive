# Hop-Simulation

## Core Concept

- for loop

- 

```java
if (simulate())
```
already:
1. calls the method
2. receives the returned boolean
3. checks whether it is true

so double check not to run simulation() double times.

## Time Complexity

- `simulate()`: **O(n)**, where `n` is `maxHops`
- `runSimulations(int num)`: **O(m * n)**, where `m` is `num`

