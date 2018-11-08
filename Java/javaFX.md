#### General tips

.fxml has to also be placed in the out folder. This can be done by gradle or like.



#### Load fxml + controller into object

```java
//Create FXMLLoader from fxml file
FXMLLoader loader = new FXMLLoader(
	getClass().getResource("../layout/MatchVisual.fxml"));

//Get controller-object from loader
MatchVisualController mvc = loader.getController();

//Call method in controller
mvc.doSomethingTemp();

Files:
out/ui/layout/MatchVisual.fxml
srv/ui/layout/MatchVisual.fxml
srv/ui/controller/MatchVisualController.java
```

