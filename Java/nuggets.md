Sorting an ArrayList with a HashMap using lamda.

Without lamda:

````java
private ArrayList<Team> getOrderedTeamList(HashMap<Team, Integer> teamPoints){

        ArrayList<Team> teamPointsOrderedList = new ArrayList<>();
        ArrayList<Team> tempTeamsList = new ArrayList<>(teams);

        while(tempTeamsList.size() != 0){
            Team teamWithMostPoints = tempTeamsList.get(0);

            //Find the team with the most points
            for(Team team : tempTeamsList){
                if(teamPoints.get(team) > teamPoints.get(teamWithMostPoints))
                    teamWithMostPoints = team;
            }

            teamPointsOrderedList.add(teamWithMostPoints);
            tempTeamsList.remove(teamWithMostPoints);
        }

        return teamPointsOrderedList;
    }

````



With lamda:

```java
private ArrayList<Team> getOrderedTeamList(HashMap<Team, Integer> teamPoints){

        ArrayList<Team> sortedTeams = new ArrayList<>(teams);
        sortedTeams.sort(Comparator.comparingInt(teamPoints::get));
        return sortedTeams;
    }
```





#### SOMETHING

```
//Game objects
if(removeQueue.size() != 0){
    for(RenderObject removeQueueObject : new ArrayList<>(removeQueue)){
        gameObjects.remove(removeQueueObject);
        world.destroyBody(removeQueueObject.getBody());
        removeQueue.remove(removeQueueObject);
    }
}
```

