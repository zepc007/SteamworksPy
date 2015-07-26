# SteamworksForPython
Howdy!  This is a branch of Easimer's SteamworksForPython in an attempt to bring a fully-functional Python module for Steam out for the public.

Feel free to fork or contribute to this module.

# Some Notes
While I am still tinkering away with this, here are some things to note:

- You will need the Steamworks SDK
- You will most likely need a Steamworks account, with a valid AppID, to use more advanced functions (set achievements, set stats, etc.)
- You will need to be logged into Steam for anything to function, obviously.  As it assumes the game is run from Steam itself and is online.

# How To (Linux)
1. Download and unpacked the Steamworks SDK
  - In Linux, I have placed it in the home folder
2. Download this repo and unpack it inside the Steamworks SDK
  - Place it in /sdk/public/
3. On Linux, run make and it should create the libsteampy.so
4. Place the libsteampy.so, steamworks.py in your project's folder
  - These files must be together unless you modify the steamworks.py to find the libsteampy.so
5. Like the examples, add this to your project main file:
```
from steamworks import *
#Initialize Steam
Steam.Init()
```
From here you should be able to call various functions of the steamworks.py; use the steamworks.py to see what you can call from your Python project.

# Advanced Features
- Achievements
  Setting achievements works fine. Calling SteamUserStats.SetAchievement(ACHIEVEMENT-NAME) will set the Steam achievement with ease; 'ACHIEVEMENT-NAME' needs to be set to whatever you named the achievement in Steamworks.
- Statistics
  Much like achievements, calling SteamUserStats.SetStat(STAT-NAME, STAT-INCREMENT) will set the Steam statistic appropriately. Much like above, STAT-NAME needs to be whatever was set for your statistic in Steamworks.
- Getting User Statistics
  Calling SteamUserStats.RequestCurrentStats seems to respond with False. Not sure if I am implementing it wrong currently or perhaps it is coming back in an unexpected format.
# More To Come
I am still digging through the code and trying to get more functions like setting achievements and stats, but these definitely require a Steamworks account and AppID.  Without your game on Steam, I don't think you can really use those functions but I haven't actually tested it yet.  I will update more later, especially the Windows how-to as I have not spent time on it.
