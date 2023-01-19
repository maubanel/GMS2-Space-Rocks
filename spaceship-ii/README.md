![](../images/line3.png)

### The Spaceship II

<sub>[previous](../spaceship-i/README.md#user-content-the-spaceship-i) • [home](../README.md#user-content-gms2-ue4-space-rocks) • [next](../shooting/README.md#user-content-shooting)</sub>

![](../images/line3.png)

Finishing up the movement of the space ship

<br>

---


##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now you cannot endlessly accelerate and you have a maximum speed.  The only issue now is that if you let go you never stop.  Even in space there is a small amount of friction.

![frictionless ship in game with max speed](images/ShipMaxSpeed.gif)

![](../images/line2.png)

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

Open up **spr_ship | Create** event and add a `ship_friction` variable.  Make sure the amount is **less** than the acceleration or you will never get enough energy to overcome the frictional force.

![add ship_friction variable](images/shipFriction.png)

![](../images/line2.png)

##### `Step 3.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Open up **obj_ship | Step** event and subtract the **ship_friction** from the **speed** variable.  Make sure it is placed before the clamp as we DO NOT want the **speed** variable to go below `0` which the clamp is taking care of.

![add friction to step](images/addFrictionStep.png)

![](../images/line2.png)

##### `Step 4.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now you can tune your acceleration, turn speed and friction to your liking.  When you are done we are finished with the space ship physics.

![play game and see final physics](images/FinishedShipPhysics.gif)

![](../images/line2.png)

##### `Step 5.`\|`SPCRK`| :small_orange_diamond:

Select the **File | Save Project** then press **GameMaker | Quit** to make sure everything in the game is saved. 

![save and quit](images/saveQuit.png)

___


![](../images/line.png)

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - Shooting">

![](../images/line.png)

| [previous](../spaceship-i/README.md#user-content-the-spaceship-i)| [home](../README.md#user-content-gms2-ue4-space-rocks) | [next](../shooting/README.md#user-content-shooting)|
|---|---|---|
