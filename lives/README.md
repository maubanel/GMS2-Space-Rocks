<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### Lives, Winning and Losing

<sub>[previous](../score/README.md#user-content-score) • [home](../README.md#user-content-gms2-ue4-space-rocks) • [next](../waves/README.md#user-content-launch-waves)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

Lets deal with getting killed in the game by respawning.  Lets add a certain amount of lives.  If you win go to the win screen and if you lose to the losing screen.

<br>

---


##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

Open up  **obj_game | Create** event and add a variable `p1_lives` and set the number of player 1 lives to `3`.

![add p1_lives at 3 to create event of obj_game](images/p1Lives.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

Now go to **obj_ship | Collision | obj_rock** and first check to see if there are lives left.  We need to dot instance into the `obj_game` as we are not inside this object.  We can access its variables this way.  We then subtract one life then call an alarm on **obj_game**.  This is done because the ship will be destroyed and we can't have an alarm on a destroyed objetc (it is destroyed with it). We need an alarm as want to enjoy the ship exploding and we need about 4 seconds for the debris to clear.

![alt_text](images/checkLives.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Open up **obj_game** and press the <kbd>Add Event</kbd> and select a **Alarm | Alarm0** event. Spawn another ship in the middle of the room on **Depth** `0`.

![respawn player in alarm](images/gamealarmRespawn.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now run into a rock and after 4 seconds you will respawn.

![fly into rock and respawn](images/RespawnOnDeath.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`SPCRK`| :small_orange_diamond:

Open up **obj_game | Draw** and add a lives to the hud.  Draw it at `46` on the **y** just under the score.

![draw lives in obj_game hud](images/drawLives.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now the lives countdown when you die.

![lives hud in game](images/LivesHUD.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Open up **obj_ship | Collision | obj_rock** and lets spawn another rock.  We will remove this later as we will be introducing waves into the game.  But for testing losing we need a rock to kill us!

![add rock spawning to obj_ship](images/respawnRockAtPlayerDeath.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now when you hit a rock another rock spawns.

![another rock spawns upon ship destruction](images/respawnRock.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 9.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

*Right click* on **Rooms** and select **New | Room** and name it `rm_game_over`. Change the **Width** to `1024`.

![alt_text](images/rm_GameOver.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 10.`\|`SPCRK`| :large_blue_diamond:

Open up **obj_game | Draw** and add text for the lose screen. Align a red title font that says `Game Over`.  Then print in white usign the regular font the final score and instructions on how to restart.

![alt_text](images/gameOver.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 11.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: 

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now lose the game on purpose.  It works, but it is too sudden on the final death and we should delay the transition to see the ship die with another alarm set to 4 seconds.

![alt_text](images/loseGame.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>


##### `Step 12.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

Open up **obj_ship | Collision | obj_rock** and paste the code to change rooms and replace it by calling **ALarm1** on `obj_game`.  Again the ship will die so we have to call an alarm in **obj_game** and we have already used the first **Alarm0** slot. We also want to reflect 0 lives at this point as you have run out, so subtract one more life.

![call alarm to change to lose room](images/objShipAlarm1.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 13.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

Open up **obj_game** and press the <kbd>Add Event</kbd> and select a **Alarm | Alarm1** event. Add the code you copies to go to the lose room.

![add alarm 1 to obj_game to go to losing room](images/AlarmOneGame.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 14.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now there is a nice delay on the last death to the lose room.

![alt_text](images/GameOverWithAlarm.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 15.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: 

Now open up **obj_game | Step** event.  Change the **keyboard_check** to **keyboard_check_pressed**.  Otherwise when coming back from the lose screen the game will skip right past the front end screen.  This way the player has to let go of enter and press again to go back to the game, which is the expected behavior.  Now add a check for the enter key in the game over screen and restart the game if it is pressed.

![restart game](images/EndLoopToBeginning.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 16.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now we have a full loop where we can lose then restart the game.  Next on lets look at a win condition.

![lose loop complete](images/FinishedLoseLoop.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 17.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Now we will put in a win condition for testing for now.  You will need to finish it at the end when you complete the waves. Open up **obj_game| Step** and add to the bottom a check for `rm_game` then see if the score is equal or above 500.

![obj_game win condition](images/winGame.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 18.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now we need to trigger an alarm 3 seconds in the futue.  The issue with **alarms** in step events is that if the condition runs every frame (so if the next frame, the score is still => 500) then it will set the alarm again ahead 3 seconds.  So the alarm will never ring (like hitting snooze every frame).  So the **alarm** starts at `-1` then we set it to 3.  So we can put an `if (alarm[2] < 0)`.  This way the alarm will run once it is set because it has to finish before going back to `-1`.  It won't run a second time as we will be changing levels.

We also need to restart the game if the player presses the enter key.  This is **exaclty** the same as when the player is in the lose screen.  So we can just add an **or** condition so that the game restarts when a player presses `vk_enter` in either the lose or win screen.

![set alarm 2 three seconds out](images/addAlarm2Game.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 19.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Press the <kbd>Add Event</kbd> and select an **Alarm | Alarm2** event. Now switch rooms to `rm_win`.

![go to room win in alarm 2](images/alarmGoToWin2.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 20.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond:

Open up **obj_game | Draw** script and add logic for drawing text to the win screen.  WHen in the `rm_win` screen draw `You Win` in the title font in lime.  Draw the final score and instructions for how to continue in the regular low res white font.

![draw win text](images/winTextDraw.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 21.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now win the game and you should go to the **You Win** screen and restart the game with the <kbd>Enter</kbd> key.

![play game and win to finish game flow for winning](images/WinGameLoop.gif)

___

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 22.`\|`SPCRK`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Select the **File | Save Project** then press **File | Quit** to make sure everything in the game is saved. If you are using **GitHub** open up **GitHub Desktop** and add a title and longer description (if necessary) and press the <kbd>Commit to main</kbd> button. Finish by pressing **Push origin** to update the server with the latest changes.

![save, quit, commit and push to github](images/GitHub.png)

___



<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - Launch Waves">

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

| [previous](../score/README.md#user-content-score)| [home](../README.md#user-content-gms2-ue4-space-rocks) | [next](../waves/README.md#user-content-launch-waves)|
|---|---|---|
