# Free-block-prob

## Core Concept

- **`findFreeBlock(int period, int duration)`**: Walk **`minute`** from **`0`** through **`59`**. Use **`isMinuteFree(period, minute)`**. While minutes stay free, increment a **run length** **`count`**; when **`count == duration`**, the block ends at **`minute`**, so the **starting minute** is **`minute - duration + 1`** (same as **`minute - count + 1`** when **`count == duration`**). On a **busy** minute, reset **`count`** to **`0`**. If no uninterrupted free block fits **`duration`**, return **`-1`**.

- **`makeAppointment(int startPeriod, int endPeriod, int duration)`**: For each period index **`i`** from **`startPeriod`** through **`endPeriod`**, try **`findFreeBlock(i, duration)`** (each period scanned on its own). If a start minute **≠ −1**, call **`reserveBlock(i, minute, duration)`** and **`return true`**. If every period fails, **`return false`**.

## Time Complexity

- `findFreeBlock(...)`: **O(1)** in practice — **at most 61** iterations (minutes **`0`**…**`59`**), constant work each step.

- `makeAppointment(...)`: **O(p)** where **`p`** is **`endPeriod - startPeriod + 1`** (number of periods), since each call to **`findFreeBlock`** does **bounded** minute work (**O(1)** per period).
