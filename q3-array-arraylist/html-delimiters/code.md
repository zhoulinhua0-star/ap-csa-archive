```java
// (a)
public ArrayList<String> getDelimitersList(String[] tokens) {
    List<String> list = new ArrayList<String>();
    
    for (String t: tokens) {
        if (t.equals(openDel) || t.equals(closeDel)) {
            list.add(t);
        }
    }
    return list;
}

// (b)
public boolean isBalanced(ArrayList<String> delimiters) {
    int countOpen = 0, countClose = 0;

    for (String d: delimiters) {
        if (d.equals(openDel)) { 
            countOpen++; 
        } else  { 
            countClose++; 
        }

        if (countClose > countOpen) { return false; }
    }
    
    return countOpen == countClose;
}
```