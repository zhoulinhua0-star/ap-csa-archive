```java
// (a)
public int numWordsOfLength(int len) {
    int count = 0;
    for (int i = 0; i < myList.size(); i++) {
         if (myList.get(i).length() == len) { count++; }
    }
    return count;
}

// (b)
public void removeWordsOfLength(int len) {
    for (int i = myList.size() - 1; i >= 0; i--) {
        if (myList.get(i).length() == len) { myList.remove(i); }
    }
}
```
