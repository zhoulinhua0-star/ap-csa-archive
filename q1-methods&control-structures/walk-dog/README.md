# Walk-dog

## Core Concept

- **`walkDogs(int hour)`**: Compare **`company.numAvailableDogs(hour)`** to **`maxDogs`**. If availability is at or below the cap, call **`company.updateDogs`** with that count; otherwise update with **`maxDogs`**. Return **`Math.min(company.numAvailableDogs(hour), maxDogs)`** so the result never exceeds the walker’s limit.

- **`dogWalkShift(int startHour, int endHour)`**: Loop each hour **`h`** from **`startHour`** through **`endHour`** (inclusive). Add **`5 * walkDogs(h)`** to pay. Treat **9–17** as peak with **`h >= 9 && h <= 17`**. Add **$3** extra that hour if it is peak **or** if **`walkDogs(h) == maxDogs`** (walker was at capacity).

## Time Complexity

- `walkDogs(int hour)`: **O(1)**

- `dogWalkShift(int startHour, int endHour)`: **O(n)**, where **`n`** is the number of hours in the shift **`endHour - startHour + 1`** (one iteration per hour; each step does **O(1)** work aside from **`walkDogs`** calls).
