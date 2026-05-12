# WordPair

## Core Concept

### Nested for loop 

```java
for (int i = 0; i < words.length - 1; i++) {
    for (int j = i + 1; j < words.length; j++) {

    }
}
``` 

is equivalent to:

```java
 int idx = 0;
while (idx < words.length - 1) {
    for (int i = idx + 1; i < words.length; i++) {
       
    }
    idx++;
}
```

### Composition

e.g.

```java
allPairs.add(new WordPair(words[idx], words[i]));
```

```java
if (pair.getFirst().equals(pair.getSecond())) {
            count++;
}
```

## Time Complexity

- `WordPairList(String[] words)`: **O(n^2)**, where `n` is `words.length`

- `numMatches()`: **O(m)**, where `m` is `allPairs.size()` 

