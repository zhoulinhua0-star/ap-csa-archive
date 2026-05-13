```java
// (a)
public Round(String[] names) {
    competitorList = new ArrayList<Competitor>();

    for (int i = 0; i < names.length; i++) {
        competitorList.add(new Competitor(names[i], i + 1));
    }
}

// (b)
public ArrayList<Match> buildMatches() {
    ArrayList<Match> list = new ArrayList<Match>();

    if (competitorList.size() % 2 == 0) {

        for (int i = 0; i < competitorList.size() / 2; i++) {
            Match match = new Match(competitorList.get(i), 
                competitorList.get(competitorList.size() - 1 - i);
            list.add(match);
        }

    } else {

        for (int i = 0; i < competitorList.size() / 2 + 1; i++) {
            Match match = new Match(competitorList.get(i), 
                competitorList.get(competitorList.size() - i);
            list.add(match);
    }
    
    return list;
}