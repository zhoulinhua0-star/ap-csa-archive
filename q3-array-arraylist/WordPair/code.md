```java
// (a)
public WordPairList(String[] words) {
    allPairs = new ArrayList<WordPair>();
    
    int idx = 0;
    while (idx < words.length - 1) {
        for (int i = idx + 1; i < words.length; i++) {
            allPairs.add(new WordPair(words[idx], words[i]));
        }
        idx++;
    }
}

// (b)
public int numMatches() {
    int count = 0;
    for (WordPair pair: allPairs) {
        if (pair.getFirst().equals(pair.getSecond())) {
            count++;
        }
    }
    return count;
}
```