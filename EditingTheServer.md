# Editing your new Epoch Server
If you've made it this far and succesfully loaded into your own server, congrats! Now it's time to start modding it to fit what you want.But before you do that I HIGHLY recommend making backups of your "@DayZ_Epoch_Server" and your "MPMissions"  folder regularly. I'm going to add some simple mods to get you started.
# Making Edits
* Before adding mods, you should go navigate to `DZE_Server_Config\BattleEye\scripts.txt`and change all the `5`s to `1`, this where Notepad++ comes in handy. 
* Open the `scripts.txt` in VS Code, Ctrl + A, then Ctrl + C, now open up Notepad++ and hit Ctrl + V, everything in `scripts.txt` should be pasted into Notepad++. 
* Now, In Notepad++ at the top there will be a bunch of icons, all the way to the right there is a Circle icon, it says “start recording” when you hover over it, go ahead and click it, once you do it will become unclickable. 
* Now go to line 2 -> begins with `5 addAction`, click anywhere on that line, now hit the Home key on your keyboard, now hit the Right arrow key, Backspace, type `1`, then Down arrow key. Once you’ve done this go back to the top and hit the Square button right next to the Circle button we pressed earlier to Stop Recording. 
* Now to the right of them there is a Triangle Play button, you can click this 83 times, or you can click the double triangle play button, a dialog will come up asking how many time you want to run the macro you just created, I believe its 83, type `83` into the box, click run. 
* Scroll down and make sure all of them were set to `1`, if any were missed go ahead and change them. 
* Now go ahead and Ctrl + A, Ctrl + C, then navigate back to VS Code, and Ctrl + V (unless you closed it then you will need to highlight everything in the `scripts.txt` file that you have open in VS Code again before pasting into it. 
* After making edits or addings mods to the server, remember in order to start server you type the 'start start' command in the terminal in VS Code, as the 'Start.bat' will repack your PBO's for you. 
* If this isn't going to be a public server, but only for you and your friends and you don't need the security -> go to '11_chernarus.cfg' -> find line 'BattlEye = 1;' then set to 0, also find the line  `password = “”;` and make a good one!, if so you don’t need to follow the [Battle Eye Filters](../writeup/BattleEye.md), after installing the Admin Tools you are good to go!

# Value Edits
* Open File Explorer -> DayZ_Server -> @DayZ_Epoch -> Addons -> right click 'dayz_code' -> PBO Manager -> "Extract to dayz_code\" -> drag the "dayz_code" folder into the VS Workspace -> Add to Workspace. 
* Open it in the workspace -> find 'configVariables.sqf' -> right click -> Copy. 
* Navigate to your "DayZ_Epoch_11.Chernarus" folder in the workspace -> right click -> Paste (or Ctrl + V). 
* Now, while in that folder still -> right click on it -> New Folder -> name it 'init'. Now go back to the "dayz_code" folder -> init -> find 'variables.sqf' -> right click -> Copy. 
* Navigate back to the  "DayZ_Epoch_11.Chernarus" folder and go to the empty 'init' folder you make -> Right click -> Paste. Right click on the "dayz_code" folder in the workspace -> Remove folder from workspace. 
* Now go back to "DayZ_Epoch_11.Chernarus" folder and click on 'init.SQF'. Find this:
```ruby
call compile preprocessFileLineNumbers "\z\addons\dayz_code\init\variables.sqf";
```
and right BELOW it put:
```ruby
call compile preprocessFileLineNumbers "dayz_code\init\variables.sqf";
call compile preprocessFileLineNumbers "dayz_code\configVariables.sqf";
```
* Now to make the value edits you would like, you'll be editing `init.sqf`, `configVariables.sqf`, and `variables.sqf`. 
* If you want ZSC single currency for example, enable it in the configVariables by changing
```c
Z_SingleCurrency = false; 
```
to 
```c
Z_SingleCurrency = true;
```
* Go to `Description.ext` in your mission folder -> at the bottom find:
 ```c
 #include "\z\addons\dayz_code\Configs\CfgServerTrader\CfgServerTrader.hpp" // Normal traders
//#include "\z\addons\dayz_code\Configs\CfgServerTraderZSC\CfgServerTrader.hpp" // Single currency traders
 ```
 and change to:
 ```c
 //#include "\z\addons\dayz_code\Configs\CfgServerTrader\CfgServerTrader.hpp" // Normal traders
 #include "\z\addons\dayz_code\Configs\CfgServerTraderZSC\CfgServerTrader.hpp" // Single currency traders
 ```

# Map Addons
* We're going to add custom map addons server side. 
* Watch my [video](https://youtu.be/y639xY7ekdc) on how to make your map edits -> navigate to "dayz_server" in your workspace -> Right click -> Add new File -> name it "build.sqf' -> Add New Folder -> Name it "custom_buildings" -> grab your 'mission.sqf' file from the map edit you did -> rename it to like 'BalotaAddons.sqf'  for example if you made changes to Balota -> now place that file in the "custom_buildings" folder. 
* Navigate to "dayz_server\init\server_functions.sqf" -> find:
```ruby
call compile preprocessFileLineNumbers "\z\addons\dayz_code\loot\init.sqf";
```
then right BELOW it add:
```c
#include "\z\addons\dayz_server\build.sqf";//build custom map addons before player setup
```
* Now go to the 'build.sqf' script and type `execVM "\z\addons\dayz_server\custom_buildings\BalotaAddons.sqf";` Restart your server and the map edits you made will work.  
* Note any other addons you want to add you need to keep adding the `execVM "\z\addons\dayz_server\custom_buildings\myCustomMapBuildingScript.sqf";` lines to the build.sqf.

# Third Party Mods
For example you might see that you want Wicked AI mod on your server.
* Most 3rd party mods from github have a `readme.md` that you can follow, the good ones give you the battleye exceptions you need as well, but if you add a mod that doesn't give you the battleye exceptions you will want to run 'BE_AEG.exe' if the kicks are due to 'script restriction' and any other filter .txt file restrictions you will have to add manually.

# Installing the Admin Tools
BigEgg made some great [Anti Hack Admin Tools](https://github.com/BigEgg17/Epoch-Antihack-Admin-Tools) for the community to use and they work on Epoch 1.0.7! They let admins fly, teleport, and overall do what they need to do.
* You will want to follow the `readme.md` on the github for the installation of the admin tools until you get to `Step 11: Drag all the BattlEye filters from the BattlEye folder into your server's BattlEye folder.`, do not do that, instead come back and continue.

## Done
You are now done learning how to edit your server, please click Continue below and navigate to the `Battle Eye Filters` step.

[Click Here to Continue](../main/README.md)
