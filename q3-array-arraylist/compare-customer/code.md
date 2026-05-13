```java
// (a)
public int compareCustomer(Customer other) {
    int nameCompare = this.getName().compareTo(other.getName());
    if (nameCompare != 0) {
        return nameCompare;
    } else {
        return this.getID() - other.getID();
    }
}

// (b)
public static void prefixMerge(Customer[] list1, Customer[] list2, Customer[] result) {
    int idx1 = 0;
    int idx2 = 0;

    for (int i = 0; i < result.length; i++) {
        int comparison = list1[idx1].compareCustomer(list2[idx2]);
        
        if (comparison < 0) {
            result[i] = list1[idx1];
            idx1++;
      } else if (comparison > 0) {
            result[i] = list2[idx2];
            idx2++;
      } else {
            result[i] = list1[idx1];
            idx1++;
            idx2++;
       }
    }
}
```