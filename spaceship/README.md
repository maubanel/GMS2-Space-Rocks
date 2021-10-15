<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### The Spaceship

<sub>[previous](../setting-up/README.md#user-content-setting-up) • [home](../README.md#user-content-gms2-ue4-space-rocks) • [next](../)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

Lets start by creating the spaceship artwork and getting the physics locked down so that we can perfect the feeling of the the game.

<br>

---


##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

Open up the **Rooms** folder and rename **Room1** to `rm_game`.  Change the **Properties | Height** to `1024` and the **Properties | Width** to `728`.

![rename room to rm_game](images/renameRoomGame.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

*Right click* on **Sprites** and select **Create | Sprite** and name it `spr_ship`.  *Press* the <kbd>Resize</kbd> button (four arrows) to change the sprite. *Click* on **Resize Canvas** and change the **Width** and **Height** to `32` by `32`. Press the <kbd>Apply</kbd> button.

![resize sprite to 32 by 32](images/resize32by32.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now since we will be rotating the ship we want to change the **Origin** to `Middle Center`. Press the <kbd>Edit Image</kbd> button.

![change sprite origin to middle center](images/originMiddleCenter.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Select the white color and the second size square brush.  Press the <kbd>Polygon tool</kbd> button on the top left corner for just the outline.  Draw a triangle with a tail (so you know the ship is pointing right). Press the <kbd>Equal</kbd> button to see the sprite in its game size.

![draw spaceship with polygon tool](images/DrawSpaceship.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`SPCRK`| :small_orange_diamond:

*Right click* on **Objects** and select **Create | Object** and name it `obj_ship`.  Assign sprite `spr_ship` by pressing **Sprite** and selecting the sprite.

![create obj_ship and assign spr_ship sprite](images/objShip.png)


<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond:

Press the <kbd>Add Event</kbd> button and select the **Create** event.  Center the sprite on the screen.  Remember a **Create** event just runs once when the object is originally put into a level.  So this ensures that everytime a ship is created (maybe after it is destroyed by an asteroid) that it starts in the very middle of the level. Since our origin is center we can just divide the **[room_height](https://manual.yoyogames.com/GameMaker_Language/GML_Reference/Asset_Management/Rooms/room_height.htm)** and **[room_width](https://manual.yoyogames.com/GameMaker_Language/GML_Reference/Asset_Management/Rooms/room_width.htm)** by 2.

![set x and y to center of level](images/addShipCreateEvent.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Open up **rm_game** and drag **obj_ship** to the middle of the room.  Don't worry about being too accurate as the **Create Event** will center the ship perfectly when you run the game.

![put obj_sprite into rm_game](images/shipInRoom.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. You will see your spaceship facing right in the middle of the room with no physics.

![play game with ship in center of room doing nothing](images/shipInRoomGame.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 9.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

To rotate we will be using the polar coordinate system to rotate the space ship.  **[image_angle](https://manual.yoyogames.com/GameMaker_Language/GML_Reference/Asset_Management/Sprites/Sprite_Instance_Variables/image_angle.htm)** is used to rotate the sprite to an angle between 0 and 359 degrees.  Right is 0 degrees, up is 90, left is 180 and down is 270.  So to move counter-clockwise we are adding degrees and to rotate clockwise we are subtracking degrees. The diagram below shows the spaceship's **image_angle** set to `90` degrees.

![diagram of polar coordinate system](images/polarCoordinate.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 10.`\|`SPCRK`| :large_blue_diamond:


We are using **[keyboard_check(key)](https://manual.yoyogames.com/GameMaker_Language/GML_Reference/Game_Input/Keyboard_Input/keyboard_check.htm)** that will return `1` when a key is being held and `0` when it is not. 

We need to *subtract* degrees for moving *clockwise* (the right arrow key) and *add* degrees for moving *counter-clockwise*.  So we will be subtracting vk_right from vk_left.  This way when we are pressing *right* we will get **(0-1) or -1** and when pressing *left* we will get **(1-0) or +1**.

![alt_text](images/addSubtract.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 11.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: 

Lets take this into a script.  Open up **obj_ship** and press the <kbd>Add Event</kbd> button and select **Step | Step**.  A step event runs every frame and will be used to move our ship. Add the following steps:

1.  Subtract `vk_right` from `vk_left`.
2.  Change `image_angle` 5 degrees per frame.

In this code our when we set `image_angle = image_angle * 5`, this is adding either -5, 0 or 5 degrees  per frame. So if we are pressing left, `image_angle` starts at `0` (the default starting value of the ship facing right), then the second frame it moves to **0 + 5 or 5 degrees**. The next frame `image_angle` is now **5 degrees** and it will go to **5 + 5 or 10 degrees**. The next frame `image_angle` is now **10 degrees** and it will go to **10 + 5 or 15 degrees**. And so on and so on...


![add step event and add rotation code](images/rotateShipStep.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>


##### `Step 12.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 13.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 14.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 15.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 16.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 17.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 18.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 19.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 20.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 21.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

___


<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - ADD NEXT PAGE">

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

| [previous](../setting-up/README.md#user-content-setting-up)| [home](../README.md#user-content-gms2-ue4-space-rocks) | [next](../)|
|---|---|---|
