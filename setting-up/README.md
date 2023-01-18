![](../images/line3.png)

### Setting Up

<sub>[home](../README.md#user-content-gms2-ue4-space-rocks) • [next](../spaceship-i/README.md#user-content-the-spaceship-i)</sub>

![](../images/line3.png)

Lets get started with setting up version control and starting the project.

<br>

---


##### `Step 1.`\|`SPCRK`|:small_blue_diamond:

Pres the <kbd>New</kbd> then the <kbd>New Blank</kbd> to create a new blank project. Call the project `SpaceRocks`. Put it in the same folder that contains your **Perforce** repository. It should appear in the same folder as the first project **Getting Started**. Select this directory by pressing the <kbd>Open</kbd> button.

![start gamemaker studio 2 project called Space Rocks](images/newProject.png)

![](../images/line2.png)

##### `Step 2.`\|`FHIU`|:small_blue_diamond: :small_blue_diamond: 

Press the <kbd>Lets Go!</kbd> button to start our new project.

![press lets go](images/SelectLetsGo.png)

![](../images/line2.png)

##### `Step 3.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now you should have an empty game with the defaul room!

![empty project](images/refreshForLink.png)

![](../images/blankProject.png)

##### `Step 4.`\|`SPCRK`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Eventually you will get a link to the repository that **GitHub Classroom** has created.  *Click* on the link to your new repository.

![press link to repository](images/linkToRepository.png)

![](../images/line2.png)

##### `Step 5.`\|`SPCRK`| :small_orange_diamond:

You get to your empty repository on **GitHub**.

![empty repository](images/blankRepo.png)

![](../images/line2.png)

##### `Step 6.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond:

Open up **GitHub Desktop** and select **File | New Repository** to create a **GitHub** repository inside the **GameMaker Space Rocks** project you just created.

![alt_text](images/fileNewRepository.png)

![](../images/line2.png)

##### `Step 7.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Now we want the project to be in the same folder as the `.yyp` project filename (in this case Space Rocks).  You then need to set the **name** the exact name of the folder that holds the project.  So in my case the folder that contained the project was **Documents | GitHub**.  So I use this as the **Local Path**.  For the **Name** I use the project folder `Space-Rocks`. It has to be spelled EXACTLY the same way as the one that holds the **GameMaker** project. This way it will create a git repository in this folder without creating a new folder.

![alt_text](images/SelectProjetFolder.png)

![](../images/line2.png)

##### `Step 8.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

When you see them there has to be a `.git` hidden folder in the **same** directory as the project file (in my case **Space-Rocks.yyp**).

![.git folder in the same folder as project file](images/SpaceRocksGitDir.png)

![](../images/line2.png)

##### `Step 9.`\|`SPCRK`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Press **Repository | Open in Terminal** on mac and **Repository | Open in ???** on PC.

![create new repository in project folder](images/CreateNewRepository.png)

Now the only way we know that it works properly is to turn on the ability to see hidden files and folders.  Go to [Microsoft Resources](https://support.microsoft.com/en-us/windows/show-hidden-files-0320fe58-0117-fd59-6851-9b7f9840fdb2) for windows 10 instructions for turning on hidden files and folders.  Read this [article](https://www.macworld.co.uk/how-to/show-hidden-files-mac-3520878/) for instructions on the mac.


![](../images/line2.png)

##### `Step 10.`\|`SPCRK`| :large_blue_diamond:

You now need to connect this new repository to the one you created in the second step in this walk through.  Copy and paste the line that includes `git remote add origin`... and press enter.

![add origin for github repository](images/setRemoteGitHub.png)

![](../images/line2.png)

##### `Step 11.`\|`SPCRK`| :large_blue_diamond: :small_blue_diamond: 

Now type `git push -u origin main` to push your work to **GitHub**.  The project is now set up and you will be able to use **GitHub** desktop without command line for the rest of the project.

![alt_text](images/PushToGitHub.png)


![](../images/line.png)

<!-- <img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - The Spaceship I"> -->
![Next Up ](images/banner.png)

![](../images/line.png)

| [home](../README.md#user-content-gms2-ue4-space-rocks) | [next](../spaceship-i/README.md#user-content-the-spaceship-i)|
|---|---|
