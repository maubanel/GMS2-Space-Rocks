<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### Front End

<sub>[previous](../next-size/README.md#user-content-spawn-next-size-rock) • [home](../README.md#user-content-gms2-ue4-space-rocks) • [next](../score/README.md#user-content-score)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

Lets look at implementing a start screen. Lets have some rocks floating in the background with a title and instructions on how to play the game.

<br>

---


##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

*Right click* on **Rooms** and select **New | Room** and name it `rm_front_end`. Change the **Room Order** to place this room on the top of the list. Change the **Width** to `1024`.

![add rm_front_end and put on the top of room order](images/rmFE.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

*Right click* on **Objects** and select **New | Object** and name it `obj_game`. Press the <kbd>Add Event</kbd> and select a **Other | Room Start** event. This will run once each time a room is changed.  This object will be used to control all game states. 

![add obj_game with a room start event](images/objGameRoomStart.png)

Drag **obj_game** into **rm_front_end**.

![add obj_game to room fe](images/addGameToFE.png)

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

Open up **obj_game | Draw** and change the font to white and to **fnt_low_res**.  Center it on **x** and place it `300` on the **y**.  Add a score goal, instructions for how to play the game and direction sfor how to start.  Please note that `\n` will not print this will be a line return in the game and just move to the next line (like <br> in html).

![alt_text](images/draw_game_instructions.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 16.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now you should see the instructions we printed above in the game.

![full instructions for front end](images/spaceRocksTitleInGame.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 17.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Go back to **obj_game** and press the <kbd>Add Event</kbd> and select a **Step | Step** event. Then check to make sure we are in the first room, if we are then we can change rooms to the game!

![add step event for obj_game then check for enter key press in fe level](images/stepFEGame.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 18.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now you can move from the front end to the game.

![go from front end to game](images/FEtoGame.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 19.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:
 Now we want the **obj_game** to persist from level to level.  We are going to use it for all of our master game logic that transends the front end, game and win/lose screens. But if we run the game in debug mode and look at what instances are in the room, we see it in the **rm_front_end** but not in **rm_game**.  How do we make **obj_game** persist from room to room?

![obj_game missing in game](images/objGameMissing.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 20.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond:

Open up **obj_game** and set **[persistent](https://manual.yoyogames.com/GameMaker_Language/GML_Reference/Asset_Management/Instances/Instance_Variables/persistent.htm)** to `true`.

> This variable can be read to find out if the instance is flagged as persistent or not, or it can used to set persistence to true (persistent) or false (not persistent) for the instance. A persistent instance is one that will be "carried over" from room to room, meaning (for example) that it only has to be created once at the start of the game and it will be present in all further rooms. Care should be taken with persistence as it is easy to lose track of persistent instances which can lead to problems later in the development of the game. - GameMaker Manual

So we will be careful with this object and it will be the only persistent one in the game.

![make obj_game persistent](images/objGamePersistent.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 21.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond:

*Press* the **Debug Play** button and look at the **Instances**.  You will notice that now **obj_game** no longer disappears and moves into the **rm_game**.

![debug play to ensure obj_game persists](images/debugObjGameInGame.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 22.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Select the **File | Save Project** then press **File | Quit** to make sure everything in the game is saved. If you are using **GitHub** open up **GitHub Desktop** and add a title and longer description (if necessary) and press the <kbd>Commit to main</kbd> button. Finish by pressing **Push origin** to update the server with the latest changes.

![save, quit, commit and push to github](images/GitHub.png)
___


<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - Score">

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

| [previous](../next-size/README.md#user-content-spawn-next-size-rock)| [home](../README.md#user-content-gms2-ue4-space-rocks) | [next](../score/README.md#user-content-score)|
|---|---|---|
