### Operator overload
````c#
readonly private Item[] allIngameItems;


public ItemDropManager() : this(new SaveFileHandler()) { }

public ItemDropManager(SaveFileHandler saveFileHandler) : this(saveFileHandler.loadAllIngameItems()) { }

public ItemDropManager(Item[] allIngameItems)
{
  if (allIngameItems.Length == 0)
    throw new ArgumentException();

  this.allIngameItems = allIngameItems;
}
````
