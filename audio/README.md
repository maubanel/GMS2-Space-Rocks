<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### Audio

<sub>[previous](../waves/README.md#user-content-launch-waves) • [home](../README.md#user-content-gms2-ue4-space-rocks)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

After you have completed the game loop and added escalation, we can put the finishing touch with adding audio to the game. 

<br>

---

##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

Lets add a shooting sound effect.  Download the [snd_zap.ogg](../Assets/snd_zap.ogg) file.  *Right click* on **Sounds** and select **Create Sound**.  Call the file `snd_zap`.  Press the <kbd>...</kbd> button and select the file you just downloaded **snd_zap.ogg**. Press the <kbd>Play</kbd> button and hear the sound it should make.

![download snd_zap and make into an audio file in gamemaker](images/zapSound.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

Where does the shooting take place. It is in the **obj_ship | Step** event.  We need to look to where we check to see if the spacebar is pressed.  This is where we will play the sound.  We will be using **[audio_play_sound(index, priority, loop);](https://manual.yoyogames.com/GameMaker_Language/GML_Reference/Asset_Management/Audio/audio_play_sound.htm)**

> With this function you can play any sound resource in your game. You provide the sound index and assign it a priority, which is then used to determine how sounds are dealt with when the number of sounds playing is over the limit set by the function audio_channel_num(). Lower priority sounds will be stopped in favour of higher priority sounds, and the priority value can be any real number (the actual value is arbitrary, and can be from 0 to 1 or 0 to 100, as GameMaker Studio 2 will prioritize them the same). Note that when dealing with priority, the higher the number the higher the priority, such that a sound with priority 100 will be favoured over a sound with priority 1. The final argument is for making the sound loop and setting it to true will make the sound loop until it is stopped and setting it to false will play the sound once only. <br><br>This function will also return a unique index number for the sound being played which can then be stored in a variable so that you can then pause it or stop it with the appropriate functions. This means that if you have multiple instances of the same sound playing at any one time you can target just one instance of that sound to deal with using the audio functions. - GameMaker Manual

We will set the **index** to `snd_zap`, the **priority** to `1` (we have more than enough audio channels for this simple game) and `false` to **loop**.  We don't want this sound to loop (typically we would loop music that we want to start over from the begining).

![audio play sound snd_zap in shooting code](images/audioPlayZap.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Press the <kbd>Space Bar</kbd> and you should have a shooting sound. Make sure you unmute the video to hear what it should sound like.

https://user-images.githubusercontent.com/5504953/138128316-6f23ebba-bcbe-4fe1-83b9-36b10ee8c986.mp4


<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Lets add a rock blowing up sound effect.  Download the [snd_die.ogg](../Assets/snd_die.ogg) file. *Right click* on **Sounds** and select **Create Sound**.  Call the file `snd_zdie`.  Press the <kbd>...</kbd> button and select the file you just downloaded **snd_die.ogg**. Press the <kbd>Play</kbd> button and hear the sound it should make when a rock of the spaceship is killed.

![download and link snd_die.ogg](images/sndDie.png)


<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`SPCRK`| :small_orange_diamond:

Open up **obj_rock | collision | obj_bullet** and add to the top of the collision event this explosion sound.

![download and link snd_die.ogg](images/audioPlayDie.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now you can hear both the shooting and the rocks getting hit.  There is no sound when a rock hits a player.

https://user-images.githubusercontent.com/5504953/138130572-c5738019-bc33-4bb0-97ec-c44ead954c73.mp4

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:


Now when the ship collides with the rock we need to make a sound.  Open up **obj_ship | Collision | obj_rock** and add another call to `snd_die` at the top of the script.

![alt_text](images/shipCollisionRock.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now you can hear both the shooting and the rocks getting hit.  There is no sound when a rock hits a player.

https://user-images.githubusercontent.com/5504953/138130661-289f0c11-0398-4d6a-a80d-886f393f494c.mp4

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 9.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Lets add some music to the game.  Download the [snd_song.ogg](../Assets/snd_song.ogg) file. *Right click* on **Sounds** and select **Create Sound**.  Call the file `snd_song`.  Press the <kbd>...</kbd> button and select the file you just downloaded **snd_song.ogg**. 

![download and import snd_song.ogg](images/sndSong.png)


<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 10.`\|`SPCRK`| :large_blue_diamond:

Now open up **obj_game | Room Start** and we want to first check to see if the song is playing.  Since it is on loop and plays indefinitely we don't want to accidentally start another song on top fo one already playing.

We use the function **[audio_is_playing(sound);](https://manual.yoyogames.com/GameMaker_Language/GML_Reference/Asset_Management/Audio/audio_is_playing.htm)**

> This function will check the given sound to see if it is currently playing. It sees if this sound is  playing and the function will return true otherwise it will return false. -GameMaker Manual

So we are checking for the inverse by looking for `!audio_is_playing(snd_song)` so we are looking to see if the sound **IS NOT** playing (`!` means logical not). We are also setting **Loop** to `true` as we want the song to keep playing over and over again.

![play song in room start of obj_game](images/playSong.png)


<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 11.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: 

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Notice that we have music that goes from room to room!

https://user-images.githubusercontent.com/5504953/138132003-3ca06d00-e704-47ea-aa56-147ca35a8f89.mp4

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>


##### `Step 12.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

Lets add a win and lose track to the game.  Download the [snd_win.ogg](../Assets/snd_win.ogg) and [snd_lose.ogg](../Assets/snd_lose.ogg) files. *Right click* on **Sounds** and select **Create Sound**.  Call the file `snd_win` on the first and `snd_lose` on the second.  Press the two <kbd>...</kbd> button and select the files you just downloaded **snd_win.ogg** & **snd_win.lose**. 

![add a snd_win and snd_lose ogg to the game](images/winLoseSounds.png)


<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 13.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

You should now have a proper win condition so go to the **obj_game | Step** event and stop playing the song. Then we will start playing the win track in the win room. I uncommented mine back out just so it will play.

![stop playing audio](images/reactivateWinCondition.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 14.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

Now open up **obj_game | Alarm2** where we switch to the win room and play the win song and don't have it loop.

![alt_text](images/playWinSong.png)


<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 15.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: 

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now you should hear the win music when the win condition is achieved.

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 16.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

Open up **obj_ship | Collision | obj_rock** and kill the song when the player has run out of lives.

![kill song when player loses](images/objShipDiesStopSongLose.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 17.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Now add the lose sound when you go to the **You Lose!** screen. Open up **obj_game | Alarm1** and add this before changing rooms.

![play lose sound in obj_game alarm1](images/alarm1LoseSound.png)


<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 18.`\|`SPCRK`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now you should hear the lose music when you run out of lives.

That's it for audio and the game. Select the **File | Save Project** then press **File | Quit** to make sure everything in the game is saved. If you are using **GitHub** open up **GitHub Desktop** and add a title and longer description (if necessary) and press the <kbd>Commit to main</kbd> button. Finish by pressing **Push origin** to update the server with the latest changes.

![save, quit, commit and push to github](images/GitHub.png)


| `gms2.space.rocks`\|`THE END`| 
| :--- |
| **That's All Folks!** That's it for space rocks. |

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=The End!">

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

| [previous](../waves/README.md#user-content-launch-waves)| [home](../README.md#user-content-gms2-ue4-space-rocks) |
|---|---|
