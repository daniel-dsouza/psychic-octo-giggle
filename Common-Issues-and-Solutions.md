## News
Check our [latest news](https://github.com/starcitizen-lug/information-howtos/wiki#news) for temporary issues and workarounds.

## Black or flickering window that ends with a crash, possible errors 15006 or 30007
Check for larger resolutions and scaling settings.  See this support article:

https://support.robertsspaceindustries.com/hc/en-us/articles/360000081887-Guide-to-Graphic-Issues#large-res

## Game hangs at splash screen
Try changing to a different DXVK version in the Lutris settings.  Alternate DXVKs can be quickly installed using our [LUG Helper](https://github.com/starcitizen-lug/lug-helper).

## Launcher hangs / stops responding / crashes with an "ASAR" error
Some people report the launcher hanging in combination with the Lutris runtime. If you are on Lutris, try toggling "Disable Lutris runtime" under "System options" of the Lutris game options.

If you do need to disable the Lutris runtime, the Lutris guys would like to have a log file to debug the issue. You can run lutris -d from the terminal after enabling Wine debugging as per this image:

![Enable Wine debugging](https://robertsspaceindustries.com/imager/Xeh-bNe8P9_WE60v7iLpmeXXLzI=/fit-in/400x400/https://cdn.discordapp.com/attachments/540589766811451392/558481590687236096/Peek_2019-03-22_05-43.gif)

And send a log to @beniwtv on Spectrum or send it to Lutris developers in the Lutris Discord.


## Game crashes when going to Lorville / ArcCorp or crashes often when launching
Make sure you followed the guide to install Wine's dependencies and set your vm.max_map_count as described in the installation section.


## Game crashes with " 00adntdll:FILE_GetNtStatus Converting errno 12 to STATUS_UNSUCCESSFUL "
Make sure you have set your vm.max_map_count as described in the installation section.


## Game crashes after clicking 'Launch'
This could have many causes. Your best bet is to check the Wine output and/or "game.log" file. See common causes below:

### Possible cause 1:

Many keyboards and mice can also have a "joystick" part in Linux, which Wine can detect. Unfortunately, Wine may be confused about it, as they are not real joysticks. In this case, the game could crash. Try running the Wine joystick control panel "wine control" (in Lutris: right click -> Joystick configuration) and disable your keyboard and/or mice.
This will not affect how your keyboard and mice work in the game.


## Some of your joysticks disappear / aren't recognized in the game
If you are using Lutris, make sure "Autoconfigure joypads" is turned off in the game settings for Lutris (right-click -> Configure).
Then execute the wine joystick control panel (in Lutris: right-click -> Joystick configuration) and set your joysticks there.


## Some of your joystick axis aren't recognized / don't map
Check that the game has not set the deadzone for this axis to 100%


## Launcher crashes on load / white screen / error DCompositionCreateDevice
That's an issue by the launcher using the compositor that fails for some players.
To prevent the crash, use a override option like this:

`wine "RSI Launcher.exe" "--use-gl=osmesa"`

If using Lutris, configure Star Citizen (right-click -> Configure), go to Game options, and add `"--use-gl=osmesa"` to the Arguments field.

## Workarounds For In-Game Bugs and Annoyances
https://robertsspaceindustries.com/spectrum/community/LUG/forum/149/thread/known-workarounds-for-game-bugs-and-annoyances
> Join the org to access Spectrum links: https://robertsspaceindustries.com/orgs/LUG