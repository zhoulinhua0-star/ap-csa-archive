```java
// (a)
public int scoreGuess(String guess) {
    int count = 0;
    for (int i = 0; i < secret.length() - guess.length(); i++) {
        if (secret.substring(i, i + guess.length()).equals(guess)) {
            count++;
        }
    }
    return count * guess.length() * guess.length();
}        

// (b)
public String findBetterGuess(String guess1, String guess2) 
{
    int score1 = scoreGuess(guess1);
    int score2 = scoreGuess(guess2);
    
    if (score1 == score2) {
        if (guess1.compareTo(guess2) > 0) { return guess1; }
        else { return guess2; }
    } else if (score1 > score2) {
        return guess1;
    } else {
        return guess2;
    }
}
```