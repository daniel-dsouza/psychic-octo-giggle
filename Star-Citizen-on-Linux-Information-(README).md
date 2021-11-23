## Welcome!

This is a mirror of the readme located in the [LUG's Spectrum Forum](https://robertsspaceindustries.com/spectrum/community/LUG/forum/149/thread/star-citizen-on-linux-information-thread-readme) and may end up out of date from time to time.  For the most up to date information, see the official readme located there.

Join us! https://robertsspaceindustries.com/orgs/LUG

## Easy Anti-Cheat

* We are currently waiting for more info from CIG

## Quick-Start Guide

1. Install wine-stable (or just the dependencies) on your system following this guide: https://www.gloriouseggroll.tv/how-to-get-out-of-wine-dependency-hell/
2. Install Lutris: https://lutris.net/downloads/
3. Download our LUG-Helper from: https://github.com/the-sane/lug-helper/releases
4. Launch the LUG-Helper and run the Pre-flight Check to optimize your system settings
5. In the LUG-Helper, select Manage Lutris Runners, and install the latest runner from GloriousEggroll (Or ask us in Spectrum chat which runner is currently best)
6. Optional: Select Manage DXVK Versions and install the latest dxvk from Sporif Async
7. Install the Star Citizen launcher to an SSD (we do not recommend an HDD): https://lutris.net/games/star-citizen/
8. After the launcher installs, close it. Configure Lutris to use the installed runner. Right click the game->Configure->Runner Options->Wine version
9. Optional: Check Show advanced options to configure DXVK version. Select Manual then overwrite it with the folder name of the downloaded dxvk
10. Optional: Enable Fsync if you have an Fsync-enabled kernel
11. Under System options, make sure Prefer system libraries is Off.
12. Run the launcher and install the game. See you in the 'verse!

> If you encounter a white launcher, add the --use-gl=osmesa argument in Lutris: Right click the game->Configure->Game options->Arguments

> On first launch, the game will stutter with low FPS while shaders are compiled and caches are filled. As you run/fly around and travel to different places, performance will increase.
> This can also occur after updating Star Citizen, your graphics driver, Wine, or DXVK.


> (Nov 13 2021) We currently recommend the GloriousEggroll 6.19 runner. 6.20 does not work for everyone.

> (Nov 13 2021) Note to Nvidia users: Driver 495 may not work. Use 470 instead.

## Manual Installation

**To check and set vm.max_map_count temporarily**
```
sysctl vm.max_map_count => To check the value
sudo sysctl -w vm.max_map_count=16777216 => To set it temporarily
```

**To set vm.max_map_count permanently**

_Manjaro / Antergos / Arch / Arch-based (probably) / Ubuntu (and probably derivatives) / Fedora_

* Create a new file in `/etc/sysctl.d/`
* To name the file, the leading number is the priority of the file and the ending is `.conf`. For example, `"/etc/sysctl.d/20-max_map_count.conf"`.
* Add the following line to the file:
`vm.max_map_count = 16777216`

* To reload it, run `sudo sysctl --system`


_Distributions that use sysctl.conf_

* Append the same line to `/etc/sysctl.conf`
* To reload it, run `sudo sysctl -p`


**Installing**

* Install vanilla Wine 6.4+ or a custom Runner **(As of 3.13 we recommend a runner built for Star Citizen - see Special LUG Wine Builds below)**
* Create your wine prefix: `WINEPREFIX=~/path/you/want/to/Star-Citizen winecfg`

* In the window that pops up, select **Windows 10** as Windows version and click OK
* Install winetricks from either your distribution or https://github.com/Winetricks/winetricks (if your winetricks doesn't have at least DXVK 1.6)
* Run: `winetricks corefonts dxvk vcrun2017 win10`

* Then you can run the RSI installer as normal.
* ONLY if you have black textures ingame, copy **d3dcompiler_47.dll** from the launcher directory to the games bin64/ directory, replacing the game's version.

If you have trouble installing recent Wine versions on a Debian-based distro due to missing faudio, see:

https://www.linuxuprising.com/2019/09/how-to-install-wine-staging-development.html

## Performance tuning

**Nvidia notes**

By default Nvidia has a combined cache for all games. As the cache fills up from other games, Star Citizen's shaders may get deleted leading to poor FPS. We recommend giving SC its own persistent cache by adding the following environment variables:

```
__GL_SHADER_DISK_CACHE=true
__GL_SHADER_DISK_CACHE_PATH="/path/you/want/for/your/cache"  (example: /home/myuser/.cache/sccache)
__GL_SHADER_DISK_CACHE_SKIP_CLEANUP=true
```

**AMD notes**

If you have an AMD GPU, you need to enable the new shader compiler, called ACO. This will make the stuttering when compiling shaders for the first time a lot better compared to LLVM. It also fixes the crash you get when walking down the stairs at Port Olisar or when approaching the elevator at Area 18.
_As of Mesa v20.2.0, RADV uses ACO by default._

To enable ACO if it is not already enabled by default, you need to add **RADV_PERFTEST=aco** to your environment variables. With Lutris this is easy, you can set it for the game in the settings for the game in Lutris, under the "System options" tab, where you'll find an option for it. If you run a manual Wine install, add/run "export RADV_PERFTEST=aco" in your shell/script you use to run the game.

**Special LUG Wine Builds**
Some of our members build wine runners tailored specifically for Star Citizen

@Molotov: https://github.com/snatella/wine-runner-sc/releases

@Raw_FoX provides runners that are tested and work for most people:
https://github.com/rawfoxDE/raw-wine/releases

If you use Lutris, you can use the LUG-Helper (below) to manage your wine runners or, to manually install:

* Put the runner download in `~/.local/share/lutris/runners/wine/` and restart Lutris
* In Lutris game configuration select the extracted runner from the pulldown menu

If you do not use Lutris, you can use the Wine build as follows:

* Put the download in a directory of your choice, for example, `~/Downloads/lug-sc-wine`
* Use `~/Downloads/your-runner/bin/wine` as Wine executable for running the game / installer.

For more information about runners, see:

https://robertsspaceindustries.com/spectrum/community/LUG/forum/149/thread/information-how-to-deal-with-the-lutris-runners
> Join the org to access Spectrum links: https://robertsspaceindustries.com/orgs/LUG

## LUG-Helper
We have a helper script which can manage Lutris runners, check/set recommended settings such as vm.max_map_count and the system's open file descriptors limit, delete your Star Citizen USER directory while preserving keybinds, and delete shaders or dxvk cache for troubleshooting purposes. It can be downloaded from:

https://github.com/the-sane/lug-helper/releases

## Other Tweaks

**Automatically Disable/Re-Enable Mouse Acceleration**

_For Gnome:_

* Configure the game within Lutris and go to `System options`. Make sure `Show advanced options` is checked. Add the following to the `Pre-launch script` field:

`/usr/bin/sh -c "gsettings set org.gnome.desktop.peripherals.mouse accel-profile flat"`

* And add the following to the `Post-exit script` field:

`/usr/bin/sh -c "gsettings set org.gnome.desktop.peripherals.mouse accel-profile default"`


## Common issues and solutions

### Launcher hangs / stops responding / crashes with an "ASAR" error
Some people report the launcher hanging in combination with the Lutris runtime. If you are on Lutris, try toggling "Disable Lutris runtime" under "System options" of the Lutris game options.

If you do need to disable the Lutris runtime, the Lutris guys would like to have a log file to debug the issue. You can run lutris -d from the terminal after enabling Wine debugging as per this image:

![Enable Wine debugging](https://robertsspaceindustries.com/imager/Xeh-bNe8P9_WE60v7iLpmeXXLzI=/fit-in/400x400/https://cdn.discordapp.com/attachments/540589766811451392/558481590687236096/Peek_2019-03-22_05-43.gif)

And send a log to @beniwtv on Spectrum or send it to Lutris developers in the Lutris Discord.


### Game crashes when going to Lorville / ArcCorp or crashes often when launching
Make sure you followed the guide to install Wine's dependencies and set your vm.max_map_count as described in the installation section.


### Game crashes with " 00adntdll:FILE_GetNtStatus Converting errno 12 to STATUS_UNSUCCESSFUL "
Make sure you have set your vm.max_map_count as described in the installation section.


### Game crashes after clicking 'Launch'
This could have many causes. Your best bet is to check the Wine output and/or "game.log" file. See common causes below:

_Possible cause 1:_

Many keyboards and mice can also have a "joystick" part in Linux, which Wine can detect. Unfortunately, Wine may be confused about it, as they are not real joysticks. In this case, the game could crash. Try running the Wine joystick control panel "wine control" (in Lutris: right click -> Joystick configuration) and disable your keyboard and/or mice.
This will not affect how your keyboard and mice work in the game.


### Some of your joysticks disappear / aren't recognized in the game
If you are using Lutris, make sure "Autoconfigure joypads" is turned off in the game settings for Lutris (right-click -> Configure).
Then execute the wine joystick control panel (in Lutris: right-click -> Joystick configuration) and set your joysticks there.


### Some of your joystick axis aren't recognized / don't map
Check that the game has not set the deadzone for this axis to 100%


### Launcher crashes on load / white screen / error DCompositionCreateDevice
That's an issue by the launcher using the compositor that fails for some players.
To prevent the crash, use a override option like this:

`wine "RSI Launcher.exe" "--use-gl=osmesa"`

If using Lutris, configure Star Citizen (right-click -> Configure), go to Game options, and add `"--use-gl=osmesa"` to the Arguments field.

## Workarounds For In-Game Bugs and Annoyances
https://robertsspaceindustries.com/spectrum/community/LUG/forum/149/thread/known-workarounds-for-game-bugs-and-annoyances
> Join the org to access Spectrum links: https://robertsspaceindustries.com/orgs/LUG

## Suggestions for a good gaming experience
https://robertsspaceindustries.com/spectrum/community/LUG/forum/149/thread/information-how-to-get-a-good-experience-with-star
> Join the org to access Spectrum links: https://robertsspaceindustries.com/orgs/LUG