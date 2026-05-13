# Compare-customer

## Core Concept

- `compareTo()` method

if `a.compareTo(b)` is positive, `a` is lexicographically (alphabetically) greater than `b`, vice versa

- one time looping through each array

Use one pointer for each array

## Time Complexity

- `compareCustomer(Customer other)`: **O(1)**

- `prefixMerge(Customer[] list1, Customer[] list2, Customer[] result)`: **O(n)**, where `n` is `result.length`

