# Sign

## Core Concept

- Fields **`str`** (message) and **`width`** (line length limit), set by **`Sign(String s, int w)`**.

- **`numberOfLines()`**: How many **`width`**-character chunks cover **`str`**. Equivalent to **`str.length() / width`** when **`str.length()`** is an exact multiple of **`width`**; otherwise add **one extra** line (**`/`** rounds down **+ 1`). (Empty string: **`0`** lines with this arithmetic.)

- **`getLines()`** (intent): **`null`** when **`str`** is **empty**. If **`str`** fits one line (**`length <= width`**), return **`str`**. Otherwise scan **`str`** in steps of **`width`**, take **`substring(i, end)`** with **`end = Math.min(i + width, str.length())`**, build a single **`String`**, inserting **`";"`** **between** lines but **not** after the **last** segment.

## Time Complexity

- `numberOfLines()`: **O(1)** 

- `getLines()`: **O(n ^ 2)** as worst case commonly summarized.
The loop runs about **`⌈n / width⌉`** times (**`n = str.length()`**), and **`substring`** visits every character roughly once (**O(n)** total substring work across all chunks). Repeated **`+=`** on **`result`** keeps rebuilding bigger strings (**roughly quadratic in **`p`**, **`p`** number of chunks), while **`StringBuilder`** keeps concatenation amortized linear in **`n`**.
