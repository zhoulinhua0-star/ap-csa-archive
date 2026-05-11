```java
// (a)
public boolean isWordChain() {
    for (int i = 1; i < wordList.size(); i++) {
        String previous = wordList.get(i - 1);
        if (wordList.get(i).indexOf(previous) == -1) {
            return false;
        }
    }
    return true;
}

// (b)
public ArrayList<String> createList(String target) {
    List<String> list = new ArrayList<String>();

    for (int i = 0; i < wordList.size(); i++) {
        if (wordList.get(i).indexOf(target) == 0) {
            list.add(wordList.get(i).substring(target.length()));
        }
    }
    return list;
}
```