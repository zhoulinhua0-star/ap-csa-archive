# Score-Guessing

## Core Concept

- **`substring(beginIndex, endIndex)`** — In Java the ending index is **exclusive**. Here each candidate slice is `secret.substring(i, i + guess.length())`, i.e. a window of length `guess.length()` starting at `i`.

- Sliding-window scan** — Slide `i` along `secret` and count how many positions match `guess` exactly (`equals`), then scale by `guess.length()²` for the score.

- **`compareTo`** — When both guesses have the **same** numeric score, break the tie by returning the **lexicographically larger** string (`guess1.compareTo(guess2) > 0` means `guess1` wins that tie).
  - Example 1 — Suppose `guess1` is `"dog"` and `guess2` is `"cat"` and both scores match. `"dog".compareTo("cat")` is positive (`'d'` > `'c'`), so the method returns **`guess1`** (`"dog"`).
  - Example 2 — Suppose `guess1` is `"cat"` and `guess2` is `"dog"` with equal scores. `"cat".compareTo("dog")` is negative, so the **`else`** branch runs and returns **`guess2`** (`"dog"`).

## Time Complexity

- `scoreGuess(String guess)`: **O(n)**, where `n` is `secret.length() - guess.length()`

- `findBetterGuess(String guess1, String guess2)`: **O(n)**
