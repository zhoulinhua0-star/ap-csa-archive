# Self-divisor

## Core Concept

- **Self-divisor** — A positive integer is a *self-divisor* when **every decimal digit** (non-zero) divides the number evenly: for each digit `d`, `number % d == 0`. If any digit is **0**, the number is **not** a self-divisor (division by zero is undefined).

- **Digit stripping (`% 10`, `/ 10`)** — Treat the integer as digits from right to left: the rightmost digit is `number % 10`. After checking that digit against the **whole** original value, chop it off with `number /= 10` and repeat until `number` is 0.

- **`digit == 0` guard** — As soon as a zero digit appears, `isSelfDivisor` must short-circuit to `false`; otherwise `% digit` would be invalid.

- **Exhaustive sweep from `start`** — Maintain `current` beginning at `start`, increment until `num` integers have satisfied `isSelfDivisor`; store hits in order in an array of length `num`.

- **Invariant for the digit loop** — After each `number /= 10`, the next digit to inspect must be the **new** rightmost digit (`number % 10`). The snippet only sets `digit` once before the loop; each iteration needs the updated rightmost digit (otherwise later digits are tested against stale values).

## Time Complexity

- **`isSelfDivisor(int number)`**: **O(d)** iterations, where **d** is the count of digits in `number`, because each pass removes one digit. For a signed 32-bit `int`, **d ≤ 10**, so treat it as constant **O(1)** relative to numeric range.

- **`firstNumSelfDivisors(int start, int num)`**: **O(k * d)** worst-case arithmetic work, where **k** is how many successive integers `(start, start + 1, …)` must be examined until **num** self-divisors appear, and each call to `isSelfDivisor` is **O(d)** with **d** bounded by digit length of candidates. Unlike a fixed-size loop, **k** is problem-dependent (self-divisors are not evenly spaced).
