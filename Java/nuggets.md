#### Sorting an ArrayList with a HashMap using lamda.

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



#### Removing object from an ArrayList without making a temp list.

```java
//Game objects
if(removeQueue.size() != 0){
    for(RenderObject removeQueueObject : new ArrayList<>(removeQueue)){
        //Do something
        removeQueue.remove(removeQueueObject);
    }
}
```

#### varargs and arrayLists

```java

ArrayList<Item> items = new ArrayList<>(otherList);
addItemsToInventory((Item[])items.toArray()); //TODO THIS LINE FAILS!! FIND ANOHTER WAY

public void addItemsToInventory(Item ... item){
    inventory.addAll(Array.asList(item));
}
```

