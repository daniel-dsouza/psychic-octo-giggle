## Installation Steps

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

## Important Information

> If you encounter a white launcher, add the --use-gl=osmesa argument in Lutris: Right click the game->Configure->Game options->Arguments

> On first launch, the game will stutter with low FPS while shaders are compiled and caches are filled. As you run/fly around and travel to different places, performance will increase.
> This can also occur after updating Star Citizen, your graphics driver, Wine, or DXVK.


> (Nov 13 2021) We currently recommend the GloriousEggroll 6.19 runner. 6.20 does not work for everyone.

> (Nov 13 2021) Note to Nvidia users: Driver 495 may not work. Use 470 instead.