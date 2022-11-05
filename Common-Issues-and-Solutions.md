## News
Check our [latest news](https://github.com/starcitizen-lug/information-howtos/wiki#news) for temporary issues and workarounds.

## Popup saying your Nvidia graphics driver is out of date
Disable DXVK NVAPI in Lutris. Right click the game -> Configure -> Runner options -> Enable DXVK-NVAPI/DLSS (set to off)

## Black or flickering window that ends with a crash, possible errors 15006 or 30007
Check for larger resolutions and scaling settings.  See this support article:

https://support.robertsspaceindustries.com/hc/en-us/articles/360000081887-Guide-to-Graphic-Issues#large-res

## Game hangs at splash screen or black/transparent window after clicking 'Launch'
Try changing to a different DXVK version in the Lutris settings.  Alternate DXVKs can be quickly installed using our [LUG Helper](https://github.com/starcitizen-lug/lug-helper).

DXVK installation instructions are available on our wiki [here](https://github.com/starcitizen-lug/information-howtos/wiki/Performance-Tuning#dxvk-async).

## Install button does nothing when trying to install Star Citizen, or Launch Game gets stuck at "launching..."
Launching Lutris in debug mode (`lutris -d`) will show a `KeyError: 'contentstatsid'` error.

Check your Lutris version. This is fixed in v0.5.11. https://lutris.net/downloads

## Lutris error: Star Citizen process exited abnormally (code: 3) : Command failed
You are likely missing 32bit drivers. Make sure the following packages are installed (names may vary depending on your distro)
- Nvidia: `lib32-nvidia-utils`
- AMD: `lib32-mesa` and `lib32-vulkan-radeon`

Additionally, explicitly set the Vulkan ICD loader in Lutris to either `Nvidia Proprietary` or `AMD RADV Open Source`
Right click the game -> Configure -> System options -> Vulkan ICD loader

## Game crashes after clicking 'Launch'
This could have many causes. Your best bet is to check the Wine output and/or "game.log" file. See common causes below:

### Possible cause 1:
Some people report changing their DXVK version fixes this. Try using our [Helper](https://github.com/starcitizen-lug/lug-helper) to download an async DXVK.

DXVK installation instructions are available on our wiki [here](https://github.com/starcitizen-lug/information-howtos/wiki/Performance-Tuning#dxvk-async).

### Possible cause 2:
Many keyboards and mice can also have a "joystick" part in Linux, which Wine can detect. Unfortunately, Wine may be confused about it, as they are not real joysticks. In this case, the game could crash. Try running the Wine joystick control panel "wine control" (in Lutris: right click -> Joystick configuration) and disable your keyboard and/or mice.
This will not affect how your keyboard and mice work in the game.


## Game crashes after clicking 'Verify'
Make sure Star Citizen is installed on drive "C:\" Check the "Library Folder" option in the launcher settings:

![Star Citizen launcher](https://media.discordapp.net/attachments/608349808956276737/927652866389340310/Screenshot_from_2022-01-03_14-56-37.png)

Additionally, make sure the wine prefix is not installed on an NTFS formatted partition.


## Launcher crashes on load / white screen / error DCompositionCreateDevice
That's an issue by the launcher using the compositor that fails for some players.
To prevent the crash, use a override option like this:

`wine "RSI Launcher.exe" "--use-gl=osmesa"`

If using Lutris, configure Star Citizen (right-click -> Configure), go to Game options, and add `"--use-gl=osmesa"` to the Arguments field.


## Game crashes with " 00adntdll:FILE_GetNtStatus Converting errno 12 to STATUS_UNSUCCESSFUL "
Make sure you have set your vm.max_map_count as described in the installation section.


## Game crashes when going to Lorville / ArcCorp or crashes often when launching
Make sure you followed the guide to install Wine's dependencies and set your vm.max_map_count as described in the installation section.


## Game crashes with "STATUS_CRYENGINE_FATAL_ERROR" in game.log
Some penguins have had success changing the Windows compatibility from Win10 to Win8.1 in the Wine configuration. Select Star Citizen in Lutris, then click the Wine button at the bottom and select `Wine configuration`:  
![](https://matrix-client.matrix.org/_matrix/media/r0/download/matrix.org/zKGOXxMOsktqYKqevqeSvYSw)  
In the Wine configuration, under the `Applications` tab, change `Windows version` to `Windows 8.1`


## Launcher freezes within a few seconds of opening
Try using a different runner. Ask on Spectrum or in our social channels which runner is currently recommended. Alternatively, you can try changing "Prefer system libraries" to ON, although this may have other side effects. Right click the game -> Configure -> System options -> Prefer system libraries


## Launcher hangs / stops responding / crashes with an "ASAR" error
Some people report the launcher hanging in combination with the Lutris runtime. If you are on Lutris, try toggling "Disable Lutris runtime" under "System options" of the Lutris game options.

If you do need to disable the Lutris runtime, the Lutris guys would like to have a log file to debug the issue. You can run lutris -d from the terminal after enabling Wine debugging as per this image:

![Enable Wine debugging](https://robertsspaceindustries.com/imager/Xeh-bNe8P9_WE60v7iLpmeXXLzI=/fit-in/400x400/https://cdn.discordapp.com/attachments/540589766811451392/558481590687236096/Peek_2019-03-22_05-43.gif)

And send a log to @beniwtv on Spectrum or send it to Lutris developers in the Lutris Discord.


## Some of your joysticks disappear / aren't recognized in the game
If you are using Lutris, make sure "Autoconfigure joypads" is turned off in the game settings for Lutris (right-click -> Configure).
Then execute the wine joystick control panel (in Lutris: right-click -> Joystick configuration) and set your joysticks there.


## Some of your joystick axis aren't recognized / don't map
Check that the game has not set the deadzone for this axis to 100%


## In Lutris, right clicking on Star Citizen and selecting "Configure" does not bring up the configuration
Completely close Lutris with `kill lutris`, delete everything inside the Lutris cache directory `~/.cache/lutris`, and relaunch Lutris.


## Installing Star Citizen on an NTFS-formatted drive
See: https://github.com/ValveSoftware/Proton/wiki/Using-a-NTFS-disk-with-Linux-and-Windows


## Workarounds For In-Game Bugs and Annoyances
https://robertsspaceindustries.com/spectrum/community/LUG/forum/149/thread/known-workarounds-for-game-bugs-and-annoyances
> Join the org to access Spectrum links: https://robertsspaceindustries.com/orgs/LUG