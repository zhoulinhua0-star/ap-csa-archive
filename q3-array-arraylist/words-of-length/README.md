# Words-of-Length

## Core Concept

When thinking about removing certain items within the arraylist, we better traversing through an arraylist backwards, from the last index to the first, as we could avoid adding `i--` within the loop.

## Time Complexity

Let `n` be `myList.size()`.

- `numWordsOfLength(int len)`: **O(n)**
- `removeWordsOfLength(int len)`: **O(n^2)**