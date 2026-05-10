```java
public class Scoreboard {
    private String team1Name, team2Name;
    private int scoreTeam1, scoreTeam2;
    private boolean team1IsActive, team2IsActive;

    public Scoreboard(String name1, String name2) {
        team1Name = name1;
        team2Name = name2;
        this.scoreTeam1 = 0;
        this.scoreTeam2 = 0;
        this.team1IsActive = true;
        this.team2IsActive = false;
    }

    public void recordPlay(int point) {
        if (team1IsActive) {
            if (point > 0) {
                scoreTeam1 += point;
            } else {
                this.team1IsActive = false;
                this.team2IsActive = true;
            }
        else {
            if (point > 0) {
                scoreTeam2 += point;
            } else {
                this.team2IsActive = false;
                this.team1IsActive = true;
            }
    }

    public String getScore() {
         String activeTeam = team1IsActive ? team1Name : team2Name;
         return scoreTeam1 + " - " + scoreTeam2 + " - " + activeTeam;
    }
}
```
