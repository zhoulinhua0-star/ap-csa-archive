```java
public class SignedText {
    private String firstName;
    private String lastName;

    public SignedText(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }

    public String getSignature() {
        if (firstName.length() == 0) {
            return this.lastName;
        } else {
            return firstName.charAt(0) + "-" + this.lastName;
        }
    }

    public String addSignature(String text) {
        String sig = getSignature();
        if (text.indexOf(sig) == 0) {
            return text.substring(sig.length()) + sig;
        } else if (text.indexOf(sig) == -1) {
            return text + sig;
        } else {
            return text;
        }
    }     

}
```