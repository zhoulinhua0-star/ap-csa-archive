# Student-score

## Core Concept

- Traversing the arrayList: 

```java
for (int i = 0; i < list.size(); i++) {

}
```

- find the largest number within the arraylist

- **Composition — *has-a* relationship** 
— e.g. 
A results object **contains** (`ArrayList<StudentAnswerSheet> sheets`). It **does not inherit** from `StudentAnswerSheet`; instead it **delegates** behavior by calling collaborators: `s.getScore(key)`, `s.getName()`, etc. That “object holds other objects and uses their methods” pattern is what AP CSA means by **composition** (contrast with **inheritance** *is-a*).

## Time Complexity

- `getScore(ArrayList<String> key)`: **O(n)**, where `n` is `answers.size()`

- `highestScoringStudent(ArrayList<String> key)`: **O(m * n)**, not **O(m)** — the outer loop runs **`m = sheets.size()`** times, but **each** iteration evaluates `s.getScore(key) > highest.getScore(key)`, and **`getScore` is O(n)** on the answer lists. Worst-case work scales with **both** how many sheets you scan (**m**) and how many questions per sheet (**n**). (Caching each sheet’s score once per iteration would still be **O(m * n)** from computing every student’s score once.)

