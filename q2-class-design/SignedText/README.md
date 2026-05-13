# SignedText

## Core Concept

- Store **`firstName`** and **`lastName`** set in the constructor.

- **`getSignature()`**: If **`firstName`** is empty (`length == 0`), return **`lastName`**. Otherwise return the first character of **`firstName`**, a hyphen, and **`lastName`** (e.g. initial + `"-"` + last name).

- **`addSignature(String text)`**: Compute **`sig`** with **`getSignature()`**, then use **`text.indexOf(sig)`**:
  - **`0`**: signature is already at the **start** — return the text **after** the signature (`substring(sig.length())`) with **`sig`** appended (move signature to the **end**).
  - **`-1`**: signature **never appears** — return **`text + sig`** (append once).
  - **Any other index**: signature appears **in the middle** — return **`text`** unchanged.

## Time Complexity

- `getSignature()`: **O(1)** for checks and **`charAt`**; the returned **`String`** is built in time proportional to the **length of the signature** (about **`lastName.length()`**).

- `addSignature(String text)`: **O(n)** where **`n`** is **`text.length()`**, dominated by **`indexOf`**, **`substring`**, and concatenation (**`sig`** length treated as bounded relative to **`n`**).
