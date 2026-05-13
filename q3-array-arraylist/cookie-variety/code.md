```java
// (a)
public int getTotalBoxes() {
    int sum = 0;
    for (int i = 0; i < orders.size(); i++) {
        sum += orders.get(i).getNumBoxes();
    }
    return sum;
}  

// (b)
public int removeVariety(String cookieVar) {
    int count = 0;
    for (int i = this.orders.size() - 1; i >= 0; i--) {
        if (this.orders.get(i).getVariety().equals(cookieVar)) {
            count += this.orders.get(i).getNumBoxes();
            this.orders.remove(i);
        }
    }
    return count;
}
```