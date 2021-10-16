<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### Asteroids I

<sub>[previous](../shooting/README.md#user-content-shooting) • [home](../README.md#user-content-gms2-ue4-space-rocks) • [next](../)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

Now that we have a ship that fires bullets, we need targets to shoot at.  The original game had three sizes of asteroids.  A large asteroid, that when shot would spawn two medium ones.  When the medium ones are destroyed they would spawn two small ones.  So adding one large asteroid to the level, adds 6 extra rocks to clear after it is destroyed (2 medium and 4 small).

<br>

---


##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

*Right click* 3 times on **Sprites** and select **New | Sprite** and name it `spr_large`, `spr_medium` and `spr_small`.  Make the large `128` by `128`.  Make the medium `64` by `64` and the small at `24` by `24`. Use a white square that is the second thickness from the left.  Use the **Polygon** tool and draw three asteroid shapes. 

![alt_text](images/ThreeAsteroids.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

Make sure the **Origin** on all of them is `Middle | Center`.

![change origin of 3 astroids to middle center](images/centerOrigin.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

*Right click* on **Objects** and select **New | Object** and name it `obj_rock`. Set the **Sprite** to `spr_rock_large`.

![add obj_rock with spr_rock_large sprite](images/objRock.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now we want to spawn new rocks to send to the player just outside the room.  We also want to `move_wrap` the rocks so that when they leave the room they come back on the other side.  Now we don't want a spawned rock to move wrap.  So we want to make sure we spawn within **half a sprite** width of the rock and the `move_wrap` **margin** is a **full** sprite_width.

![alt_text](images/stategyForSpawningMoveWrap.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`SPCRK`| :small_orange_diamond:

Press the <kbd>Add Event</kbd> and select a **Create** event.  Remember this only runs once when the rock is created.  Now we will be dealing with the launching of rocks later on so we will put in a temporary **direction** and **speed**.  We will also need a variable to hold the **width** of the sprite which will help us with the margin we will need in the `move_wrap`.  
![alt_text](images/RockCreateEvent.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond:

Press the <kbd>Add Event</kbd> and select a **Step | Step** event. Now we will want to rotate the sprite `.4` degrees per frame for a slow rotation.  We also want to `move_wrap` both horizontally and vertically with a margin of 1 sprite width.

![add step event with move wrap and rotation](images/rockStep.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now the rock should rotate and move but there is no collision with ship or with bullets.  Lets do this next.

![alt_text](images/RockFirstPass.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Lets open up **obj_rock** and press the <kbd>Add Event</kbd> button and add a **Collision | obj_bullet** event.  A collision event runs any time the object type in the calling collision event (obj_rock) collides with a bullet.  You do not want to have two reciprical events (another bullet colliding with rock) as we only need to check the collision once.  We are picking it from the rock as we will want to add some effects from the rocks location during destruction.

![add collision between rock and bullet event](images/rockBulletCollision.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 9.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

When the rock gets hit by the bullet we want to destroy both the bullet and the rock.  The first `instance_destroy()` kills the rock. The **[other](https://manual.yoyogames.com/GameMaker_Language/GML_Overview/Instance_Keywords.htm)** keyword is used to access the namespace of the object we are colliding with (just a single instance).  So since we are in the rock this would be a reference to the bullet.  When we use `with(other)` we are entering that object's namespace.  So we can destroy the bullet within the `with` statement. 

> The other instance involved in a collision event, in a with function or in a function. - GameMake Manual

![destroy rock and bullet](images/instanceDestroyRock.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 10.`\|`SPCRK`| :large_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 11.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: 

![alt_text](images/.png)

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

| [previous](../shooting/README.md#user-content-shooting)| [home](../README.md#user-content-gms2-ue4-space-rocks) | [next](../)|
|---|---|---|
