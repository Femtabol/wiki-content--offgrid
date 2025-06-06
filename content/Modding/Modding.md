# Modding

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Modding*

*Scraped on: 2025-05-02 18:39:30*

Players, modders, and hackers are able to use the game to create new and interesting levels with stories about surveillance, hacking and the Internet of Things or whatever else you are inspired to!  Off Grid is heavily moddable, with an exposed Lua API allowing anyone to edit the game.  Level editing tools enable anyone with the  Unity engine free personal edition and build mods with the same tools the development team use.  With this level of control, players can build their own content:  levels, hackable devices, apps, hacking tools, and stories - and share them with other players - a huge opportunity for players to make and experience topical and contemporary stories as they emerge in the IRL world of hacking and surveillance.


The game is made in the Unity game engine, and we have created a fairly unique pipeline to allow players to mod Off Grid using Unity as the mod editor.  The core game logic / systems are written in C# by us and from that we have created an exposed Lua API that all the gameplay is written in.  We have made some custom Unity editor tools (using asset bundles) that allow modders to download the Unity project and make their own content, using Unity's tools for the assets and our components to set up mission triggers, and writing gameplay in Lua using out Lua api, and then export them as a zip file for drm free builds, or upload them to Steam Workshop.

# Modding Topics
Off Grid has extensive modding support, users will be able to create their own missions for the game using the very same tools that the original developers use.
## The first places start are:
### Getting Started with the LevelKit:
**How to setup the LevelKit modding tools**
### Building your First Level
**How to create custom missions using LevelKit**
Otherwise... get stuck in to the rest of it here:
## Modding Manual
This is your one stop shop to all things modding in*Off Grid*. Here you can find guides as to the process of making your own mods, both how to use the Unity editor and our Off Grid tool set, descriptions of the tools and techniques, and tutorials and example code for writing Lua and making mods.
There is a heck of a lot you can mod in*Off Grid*, we specifically have made the modding tools capable of doing pretty much everything we needed in order to make levels for the game so that you can do just as much as us, and in some cases we have made the systems more powerful than we needed so that you can do more than we have in the game too.
(A good example of this is the depth that you can make branching conversations and narratives in CryptoChat and the fact that those conversations can run functions and store variables, allowing conversational choices to drastically alter the trajectory of a player's game)
Check out the table below to see the main topics and guides, each of these categories lead on to more in depth and specific articles themselves too.
| Manual |
| --- |
| [Asset Creation Pipeline](Asset_Creation Pipeline) |
| [Character Profiles](Character Profiles) |
| [Character Types and Prefabs](Character_Types_and Prefabs) |
| [Conversations](Conversations) |
| [Creating Apps](Creating Apps) |
| [Data Scripting](Data Scripting) |
| [Debugging Your Mods](Debugging_Your Mods) |
| [Device Scripting](Device Scripting) |
| [Devices](Devices) |
| [Game Progress](Game Progress) |
| [Getting Started with the LevelKit](Getting_Started_with_the LevelKit) |
| [How the SoundIDs are structured](How_the_SoundIDs_are structured) |
| [Message Templates](Message Templates) |
| [Mission Objects](Mission Objects) |
| [Mission Scripting](Mission Scripting) |
| [Pre-made Hackable Devices](Pre-made_Hackable_Devices) |
| [Setting up Doors](Setting_up Doors) |
| [Triggering Sounds](Triggering Sounds) |
| [Audio Options](Audio Options) |
| [Triggers and Examples](Triggers_and Examples) |
## Lua Apis
Here you can find all of the Api documentation for the various calls you have access to for writing mods in*Off Grid*whether it be writing your own mission scripts, hackable devices, in game apps and tools or anything else for that matter!
## A brief overview of how users will make custom missions
1. Download Unity and the provided LevelKit project
2. Follow the instructions in LevelKit's interface to create a stub mission to build upon
3. Using our modular LevelKit pieces, create the geometry and layout to tell your visual story
4. Open up the stub mission script generated by LevelKit and fill in the logic for your mission
5. Build the Mission via LevelKit and test it in your copy of Off Grid
6. Upload to Steam workshop or send to your friends
Now to go into a little more detail about those steps:
### Download Unity and the provided LevelKit project
The levelkit will be downloadable as a seperate tool on Steam as well as our website, we'll require the user to use a specific version of Unity in order to avoid any issues
### Follow the instructions in LevelKit's interface to create a stub mission to build upon
Our LevelKit tool set will walk users through the process of creating a mission from a template, after filling in a few details about their mission we'll create a stub for them to build off. this will generate the dolfer structure and base file you need to make a mod. It should look something like this:
```
/Levels/
|-- SomeMod/
|       |-- Mission-1/
|       |       |-- Bundles/
|       |       |-- Content/
|       |       |       |-- 
|       |       |-- level.json
|       |       |-- strings.lua
|       |       |-- missionImage.png
|       |-- Mission-2
|       |       |-- Bundles/
|       |       |-- Content/
|       |       |-- level.json
|       |       |-- strings.lua
|       |       |-- missionImage.png
|       |-- mod.json
|-- OtherMod/
```
### Using our modular LevelKit pieces, create the geometry and layout to tell your visual story
We've already built up quite a large library of modular mission pieces to work with, these include architecture and props.
Users can choose how fine gain they want to design, they can build entire rooms with individual wall and window pieces or use the pre-made rooms provided for them.
Part of making a mission for Off Grid is setting up what we call "MissionObjects" these are simply unity game objects with a pre-made "MissionObject" component, using Unity's editor interface users will set the type of MissionObject.
These are
* Interactable
* Trigger
* Spawn
* HackableDevice
* Generic
These objects are can be referenced in mission scripts and be set up with custom logic (see below)
### Open up the stub mission script generated by LevelKit and fill in the logic for your mission
Once the user has made a first pass on the geometry of their mission they can start writing the logic, mission scripting in Off Grid is written in Lua.
Users lua scripts contain definitions for Characters, Physical Items, Data, Networks, Objectives, Checkpoints and Devices, they also contain code that reacts to the use of MissionObjects.
For example after setting up the MissionObject "PlayerBuildingEnter" as a trigger, the user can set up a lua function that's called when the player enters the trigger volume.
Using this simple MissionObject interface that links together Unity and our lua apis modders have an incredible amount of power to create their vision.
### Build the Mission via LevelKit and test it in your copy of Off Grid
Using LevelKit's interface users can build their mission into the folder structure the game expects and then point the game towards it in order to test it.
### Upload to Steam workshop or send to your friends
Once they've tested your level thoroughly, users can follow the in game interface for uploading their mission to steam workshop.
If they're not running the steam version of the game, they can create a zip of their mission to send to friends or post to message boards for others to try out
### How to take a look at Off Grid's modding support without the tools
If you've received a copy of Off Grid without LevelKit, you can poke around some of the lua files in the data folder it order to look at the structure of our missions and apis:
Some good places to look would be:
The apostle mission script: ( perhaps try changing Joe's name to your own? )
Windows & Linux: **OffGrid_Data/StreamingAssets/Levels/NewsPaperOffice/Scripts/theapostle_mission.lua**
OSX: **OffGrid.app/Contents/Resources/Data/StreamingAssets/Levels/NewsPaperOffice/Scripts/theapostle_mission.lua**
The script for the hackable hand dryers in the apostle mission: ( Try adding your name to the "names" lua table, or updating the colors of the ui? )
Windows & Linux: **OffGrid_Data/StreamingAssets/Levels/NewsPaperOffice/Scripts/Devices/HandDryer.lua**
OSX: **OffGrid.app/Contents/Resources/Data/StreamingAssets/Levels/NewsPaperOffice/Scripts/Devices/HandDryer.lua**