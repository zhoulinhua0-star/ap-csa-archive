# HTML-Delimiters

## Core Concept

### For-each loop

General form:

```java
for (Type variableName : collection) {

}
```

**How to use:** you can replace a counted `for` over a collection like this:

```java
for (int i = 0; i < list.size(); i++) {

}
```

with:

```java
for (String token : tokens) {

}
```

This works over both **arrays** and **`ArrayList`s**.

### Initialize your list

Declare and construct the list before calling methods on it (for example, before `add`):

```java
List<String> list = new ArrayList<>();
```

## Time Complexity

- **`getDelimitersList(String[] tokens)`:** **O(n)**, where **`n`** is **`tokens.length`** (one pass over the array).

- **`isBalanced(ArrayList<String> delimiters)`:** **O(m)**, where **`m`** is **`delimiters.size()`** (one pass over the list; **`equals`** cost is treated as bounded for typical short delimiters).
