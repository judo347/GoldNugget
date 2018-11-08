# LibGdx Framework

#### Collision

````java
GameInfo: public static final short GROUNDTILE_CATAGORY_BITS = 0x0002;

GroundTile:
	fixtureDef.filter.categoryBits = GameInfo.GROUNDTILE_CATAGORY_BITS;
Item:
	// Only collide with groundTile!
	fixtureDef.filter.maskBits = GameInfo.GROUNDTILE_CATAGORY_BITS; 

````

