# Nomads
This project is about bringing Nomads back as playable faction via featured mod and make a serious attempt to 
integrate them into the main game.

We can use all the help we can get :
- coding
- modelling
- texturing
- effects improving
- testing
- mission making
- giving feedback
- and much more!

To play the coop campaign see the coop missions repository [here](https://github.com/FAForever/NomadMissions).

Be sure to visit our discord server [here](https://discord.gg/eV3wmAX) where you can help out, comment or simply keep up with progress on the mod. Everyone is welcome!

How do I play Nomads?
----------------------------
Nomads is designed to be run as a featured mod on the Forged Alliance Forever client.

To play Nomads online, simply go to the **Find games** tab on the client, and select the mod from the featured mod list, then host a game!

   - You don't need to enable any ingame version of Nomads mods, and the Nomads mod won't show up in the mod list. Running Nomads in a different manner to the one described may produce unexpected results, or not work at all.
   - The mod is always up to date thanks to the patching mechanism, so you don't need to worry about updating the mod or making sure your friends have the same version as you do!

To play Nomads offline, a little more setup is required.

1. Make sure you have downloaded the mod through the FAForever client. To do this, simply host a game of Nomads as described above. You can close the game once you get to the ingame lobby without starting.
2. Go to `C:\ProgramData\FAForever\bin\` (note: **not** program files) and find `ForgedAlliance.exe`
3. Right click on it and create a shortcut. Place this shortcut wherever is convenient for you.
4. Go into its properties (right click) and change the target:
```
C:\ProgramData\FAForever\bin\ForgedAlliance.exe /init init_nomads.lua /log C:\ProgramData\FAForever\logs\offlineNomads.log
```
5. Click on the shortcut to launch the game. Select Skirmish from the menu (Multiplayer LAN works too) and enjoy!
   - To update the mod simply follow step 1


How do I start contributing?
----------------------------
If you want to contribute, then you'll need to know how **git** works. 
Here is a nice short [tutorial](http://wiki.faforever.com/index.php?title=FAF_Dev_School_Git) to get you started.
More information for when you want to use the desktop app: [Github desktop guides](https://help.github.com/desktop/guides/)

You should get local copies of both **FAForever/fa** and **Nomads-Project/nomads**.

#### Use your lua code in a game
You should have a local copy of the code _- both FAForever/fa and Nomads-Project/nomads -_ on your computer.
Now you'll want to set up your test environment, i.e. running the game based on your local copies.

1. Inside of the nomads repository is an `init_devnomads.lua` file that you need to **copy** inside ```C:\ProgramData\FAForever\bin\```
2. You will need to open the file and edit the file paths to match the locations of where you put the local copies of the code. The lines are at the start of the file, so you can't miss them.
   - *( Make sure you don't edit the original file, to avoid problems later )*
   - Make sure you pay attention to the double slashes in the file paths, and put them into the paths or they will not work!
   - `dev_path = 'E:\\GITS\\fa'` corresponds to the fa path
   - `dev_pathnomads = 'E:\\GITS\\nomads'` corresponds to the nomads path

3. Inside the same folder, ```C:\ProgramData\FAForever\bin\```, you'll find `ForgedAlliance.exe`
4. Make a shortcut for it either by right clicking on the file and putting it in an easily accessable place or right clicking in the folder you want the shortcut to be in and making a new shortcut there. *(For example your desktop)*
5. Go into its properties (right click) and change the target:
```
C:\ProgramData\FAForever\bin\ForgedAlliance.exe /init init_devnomads.lua /EnableDiskWatch /showlog /log C:\ProgramData\FAForever\logs\dev.log
```
  - By adding `/showlog` then the log window will automaticaly appear. There is an ingame keybind to summon the log window aswell. So it depends on your own prefence if you want it from the start or not.
`/EnableDiskWatch` will ask FA to reload your changes whenever the file is changed - skipping the need to reload your game.
`/log C:\ProgramData\FAForever\logs\dev.log` will save the log in the specified location. Usefull for sharing logs incase of issues.

You're finally ready to make changes to the lua code and test them!

#### Working with issues and pull requests
The main way of communication on github is done with issues and pull requests. 
- Whenever you find a problem or have an interesting idea, then you can make an issue for that. If there already is an issue for it, then you should comment on the original one, instead of making a new issue.
- Whenever you have something of value (bugfixes/improvements/etc) to add, you can make a pull request. Other contributors can review your changes and help improve them and/or confirm their validity. Afterwards your pull request will get merged into the master branch and will be a part of the future releases. So it is not only for sending your own changes, but also for reviewing others' pull requests. Reviewing can be quite laborous, so we'd like as many people as possible doing these so changes will be of a better quality and merged a lot faster.

##### Making an issue
To make an issue about a bug/possible improvement/new feature/etc, you should go to the original repositories webpage and [create an issue there](https://help.github.com/articles/creating-an-issue/).
Don't make issues in your own forked repository unless you don't want anyone to know about them.

When making an issue, you should follow these guidlines:
- Make a seperate issue for each bug/feature. 
So we avoid cluttered issues and everything is clear. 
- Always add as much information as you can provide about the issue
  - Give a nice description of the issue *(where/when/what/how)*
  - Add the dev logs
   You can find them here: `C:\ProgramData\FAForever\logs`
  - Provide the replay too. Watch it first (after you copied the logs) to see if the same thing happens as during the game.
     
##### Making a pull request
To make a pull request with your changes for a bugfix/possible improvement/new feature/etc, you should go to the original repositories webpage and [create a pull request there](https://help.github.com/articles/creating-a-pull-request-from-a-fork/).
Most of the time pull request will be related to an issue and merging it will solve the issue. You can close an issue manually but its a lot easier if it would automaticaly close when the pull request is merged. You can achieve this by adding a [keyword and a reference to the issue](https://help.github.com/articles/closing-issues-via-commit-messages/) inside the body of your pull request message.

When making a pull request, you should follow these guidelines:
- Give a nice description of the changes *(where/when/what/how)*
- Reference all issues related to this pull request

If something doesn't work: https://xkcd.com/1597/



Map Editor
----------------------------------------
To run the Map Editor with nomads units you need to do the following steps:

1) Paste *nomads_mesh.fx* file into *effects* folder and rename it to *mesh.fx*
2) Pack *effects, env, textures, units* folders from this repository into *Z_nomad.scd* using Winrar or similar (needs to be set as *.zip* NOT *.rar*)
3) remove the mesh.fx file from the *effects* folder of the repository again
4) Paste *Z_nomad.scd* into Supcom *gamedata* folder `THQ\Gas Powered Games\Supreme Commander\gamedata`
5) Go to `%USERNAME%\AppData\Local\Gas Powered Games\SupremeCommander\cache` and delete the content of the folder

Some common issues and how to solve them
----------------------------------------
#### 1. Unknown technique NomadsUnit
If you encounter an error like this: 
```
WARNING: attempt to retrieve annotation from unknown technique NomadsUnit
WARNING: c:\work\rts\main\code\src\libs\gpggal\EffectD3D9.cpp(89) invalid effect technique requested: NomadsUnit
```
Try to run the `shader_cleaner.bat` file to fix it.
You can find this file inside your local copy of **Nomads-Project/nomads**.

#### 2. HostGame: expected 1 args, but got 2
If you encounter an error like this: 
```
WARNING: Error running OnFrame script in CScriptObject at 10043640: void CLobby.HostGame(self)
        expected 1 args, but got 2
         stack traceback:
             [C]: in function `HostGame'
             "\documents\github\fa\lua\ui\lobby\lobby.lua(6310): in function `HostGame'
```
Make sure you are using a copy of `init_devnomads.lua` from this repository and not the outdated `init_nomads.lua`


Implementing Nomads in FAF (update the current version)
----------------------------------------
1) extract the nomads loading video from *movies/* and put it in the *FAForever/movies/* folder

2) replace the *init_nomads.lua* file in the *FAForever/bin/* folder with the version from this repository

3) zip the rest of the repository (except the movie/ folder) and rename the zip to *nomads.nmd*

4) place the *nomads.nmd* file in the *FAForever/gamedata/* folder
