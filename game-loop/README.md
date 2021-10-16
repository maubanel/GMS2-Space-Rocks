<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### Main Game Loop

<sub>[previous](../next-size/README.md#user-content-spawn-next-size-rock) • [home](../README.md#user-content-gms2-ue4-space-rocks) • [next](../)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

Lets look at implementing a start screen, win screen and lose screen.  This way we should be able to complete and restart a game upon completion.

<br>

---


##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

*Right click* on **Rooms** and select **New | Room** and name it `rm_front_end`. Change the **Room Order** to place this room on the top of the list.

![add rm_front_end and put on the top of room order](images/rmFE.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

*Right click* on **Objects** and select **New | Object** and name it `obj_game`. Press the <kbd>Add Event</kbd> and select a **Other | Room Start** event. This will run once each time a room is changed.  This object will be used to control all game states.

![add obj_game with a room start event](images/objGameRoomStart.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Lets place 10 rocks in the room and randomly send them on their way. First lets make sure we are in the front end room (in other game rooms we will not want to spawn more rocks);

![send 10 rocks off in random spawning point](images/rocksFlying.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now they look a bit silly as they all move at the same speed in the same direction.

![alt_text](images/FrontEndRocksTake1.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`SPCRK`| :small_orange_diamond:

In **obj_game | Room Start** randomize the direction the rock moves in as well as the speed.

![randomize the direction and speed](images/randomDirSpd.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now the speed and direction helps but they are all starting at the same angle. Lets change this.

![Now they move at different angles and speeds](images/FrontEndRocksTake2.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Now lets add a random `image_angle` to the rock between `0` and `359`.  This means that they will all start with a different rotation and won't look so uniform.

![Add random angle to the rocks](images/addRandomAngle.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now the game rocks look a lot more natural.  Lets stop there and move on with some titles for the game.

![play game and now the rocks look a lot better](images/FrontEndRocksTake3.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 9.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Download a [advanced pixel 7 font](../Assets/advanced-pixel-7-font.zip) and a [edge of the galaxy font](../Assets/edge-of-the-galaxy-font.zip). They are both open source and available at [fontspace.com](https://www.fontspace.com).  *Unzip* the folders and you should see:

![download and unzip two fonts for game](images/TwoFonts.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 10.`\|`SPCRK`| :large_blue_diamond:

Double click the fonts to install them on your computer.  On the mac **GameMaker** noticed a change and prompted me to let them load them into the game.  If this doesn't happen save the project then restart the game to get access to these fonts.

![install fonts](images/InstallFonts.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 11.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: 

*Right click* on **Fonts** and select **New | Font** and name it `fnt_title`. Set **Select Font** to `Edge of the Galaxy` with a **Style** of `Regular` and **Size** of `56`.

![add fnt_title with a 56 point Edge of the galaxy font](images/titleFont.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>


##### `Step 12.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

Open up **obj_game** and press the <kbd>Add Event</kbd> button to add a **Draw | Draw** event to the game. Center the text alignment and make the font orange.  Change to the **fnt_title** you just created.  Draw text in the middle of the room on the **x** and at `200` pixels on the **y** axis `Space Rocks!`. 

![draw title](images/drawGameObj.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 13.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Look at that beautiful title!

![play game nice big title](images/NiceBigTitle.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 14.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

*Right click* on **Fonts** and select **New | Font** and name it `fnt_low_res`. Set **Select Font** to `Advanced Pixel 7` with a **Style** of `Regular` and **Size** of `24`.

![select 24 point low res font](images/fnt_low_res.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 15.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: 

![alt_text](images/draw_game_instructions.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 16.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

Open up **obj_game | Draw** and change the font to white and to **fnt_low_res**.  Center it on **x** and place it `300` on the **y**.  Add a score goal, instructions for how to play the game and direction sfor how to start.  Please note that `\n` will not print this will be a line return in the game and just move to the next line (like <br> in html).

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

| [previous](../next-size/README.md#user-content-spawn-next-size-rock)| [home](../README.md#user-content-gms2-ue4-space-rocks) | [next](../)|
|---|---|---|
