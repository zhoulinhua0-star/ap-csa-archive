```java
// (a)
public double getScore(ArrayList<String> key) {
    double score = 0;
    for (int i = 0; i < answers.size(); i++) {
        if (answers.get(i).equals(key.get(i))) { score++; }
        else if (answers.get(i).equals("?")) { scores -= 0.25; }
}
    return score;
} 

// (b)
public String highestScoringStudent(ArrayList<String> key) {
    StudentAnswerSheet highest = sheets.get(0);
    for (StudentAnswerSheet s: sheets) {
        if (s.getScore(key) > highest.getScore(key)) {
            highest = s;
    }
}
    return highest.getName();
}
```