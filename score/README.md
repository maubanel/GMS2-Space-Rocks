![](../images/line3.png)

### Score

<sub>[previous](../game-loop/README.md#user-content-front-end) • [home](../README.md#user-content-gms2-ue4-space-rocks) • [next](../lives/README.md#user-content-lives-winning-and-losing)</sub>

![](../images/line3.png)

Lets add a score display to the front end and game! The player will get 20 points for killing the large rock, 50 for medium and 100 for the small rock.  Since the rocks are progressively smaller and faster a larger score should be awarded.

<br>

---


##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

Open up **P4v**.  Select the top folder of the **GameMaker** project. Press the <kbd>Checkout</kbd> button.  Checkout out all files in P4V so that they are all writable (otherwise they will be read only and none of the changes will be saved). Select a **New** changelist and add a message describing the unit of work you will be performing. Press the <kbd>OK</kbd> button.

Open up the project you are working on in **GameMaker**. 

![checkout files and create new changelist](images/checkoutFiles.png)


Go to **obj_game** and press the <kbd>Add Event</kbd> and select a **Create** event. Create a new variable `p1_score` and set it to `0`.

![add create event to obj_game and create a score variable](images/addCreateEvent.png)

![](../images/line2.png)

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

Draw a score text in the front end.  It uses `draw_text` and remember to add two strings together you have to cast the real number to a string by using `string(p1_score)` as `p1_score` holds a real number variable.

Also, check to see if we are in `rm_game` and if we are set alignment to the left, color to white and font to low res.  Print the font again.

![print score in fe and game screens](images/drawScore.png)

![](../images/line2.png)

##### `Step 3.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now you should be able to see an empty score in each screen.

![alt_text](images/ScoreInGame.png)

![](../images/line2.png)

##### `Step 4.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now we can also dot instance into an ENTIRE object class.  So if we have `obj_game.sprite_index` we can access the **sprite_index** variable in **ALL** instances of this object in the room.  Since we only have one instance of hte game object it should be ok to access its variable for `p1_score`.

We need to do this because we have to open **obj_rock | Collision | obj_bullet** as this is the only place we have in the game when we know which rock is destroyed.  We just add 20, 50 and 100 points for each rock.  We have to add a final `else` and don't need to check to see if it is `sprite_index == spr_rock_small` as we have checked for large and medium so the only one left after that is small.

![add points for each rock](images/AddScoreToRocks.png)

![](../images/line2.png)

##### `Step 5.`\|`SPCRK`| :small_orange_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now shoot all the rocks and you can get up to 520 points!

![play the game shoot rocks see score advance](images/ScoringInGame.gif)

![](../images/line2.png)

##### `Step 6.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond:

Select the **File | Save Project**, then press **File | Quit** (PC) **Game Maker | Quit** on Mac to make sure everything in the game is saved.

![save, quit, commit and push to github](images/saveQuit.png)

![](../images/line2.png)

##### `Step 7.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Open up **P4V**.  Select the top folder and press the **Add** button.  We want to add all the new files we created during this last session.  Add these files to the last change list you used at the begining of the session (in my case it was `Spaceship I portion of walkthrough`). Press the <kbd>OK</kbd> button.

![alt_text](images/add.png)

![](../images/line2.png)

##### `Step 8.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now you can submit the changelist by pressing both <kbd>Submit</kbd> buttons.

![alt_text](images/submit.png)

![](../images/line.png)

<!-- <img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - Lives, Winning and Losing"> -->

![Next Up - Lives, Winning and Losing](images/banner.png)

![](../images/line.png)

| [previous](../game-loop/README.md#user-content-front-end)| [home](../README.md#user-content-gms2-ue4-space-rocks) | [next](../lives/README.md#user-content-lives-winning-and-losing)|
|---|---|---|
