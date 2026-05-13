```java
public class CalorieCount {
    private int limit;
    private int cal;
    private int protein;
    private int carb;
    private int fat;

    public CalorieCount(int limit) {
        this.limit = limit;
        this.cal = 0;
        this.protein = 0;
        this.carb = 0;
        this.fat = 0;
    }

    public void addMeal(int c, int p, int cb, int f) {
        this.cal += c;
        this.protein += p;
        this.carb += cb;
        this.fat += f;
    }

    public boolean onTrack() {
        return this.cal <= this.limit;
}
```