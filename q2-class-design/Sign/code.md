```java
public class Sign {
    private String str;
    private int width;

    public Sign(String s, int w) {
        str = s;
        width = w;
    }

    public int numberOfLines() {
        if (str.length() % width == 0) {
            return str.length() / width;
        }
        return str.length() / width + 1;
    }
    
    public String getLines() {
        if (str.isEmpty()) { return null; }

        if (str.length() <= width) { return str; }

        String result = "";
        for (int i = 0; i < str.length(); i += width) {
            int end = Math.min(end, str.length());
            result += str.substring(i, end);
            if (end < str.length()) {
                result += ";";
            }
        }
    }

}
```