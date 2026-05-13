```java
public class APLine {
    private int a, b, c;

    public APLine(int a, int b, int c) {
        this.a = a;
        this.b = b;
        this.c = c;
    }

    public double getSlope() { 
        return - (double) this.a / this.b; 
    }

    public boolean isOnLine(int x, int y) { 
        return x * this.a + y * this.b + c == 0;
    }
}
```