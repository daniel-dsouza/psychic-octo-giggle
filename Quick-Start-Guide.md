## Installation Steps

1. Install wine-staging (or just the dependencies) on your system following this guide: https://www.gloriouseggroll.tv/how-to-get-out-of-wine-dependency-hell/
2. Install Lutris: https://lutris.net/downloads/
3. Download our LUG-Helper from: https://github.com/starcitizen-lug/lug-helper
4. Launch the LUG-Helper and run the `Pre-flight Check` to optimize your system settings
5. In the LUG-Helper, select `Manage Lutris Runners`, and install the latest runner from GloriousEggroll (Or ask us in Spectrum chat which runner is currently best)
6. _Optional: Select `Manage DXVK Versions` and install the latest dxvk from Sporif Async_
7. Install the Star Citizen launcher to an SSD (we do not recommend an HDD): https://lutris.net/games/star-citizen/ _(See important information below)_
8. After the launcher installs, close it. Configure Lutris to use the installed runner. `Right click the game->Configure->Runner Options->Wine version`
9. _Optional: Check `Show advanced options` to configure `DXVK version`. Select `Manual` then overwrite it with the folder name of the downloaded dxvk_
10. _Optional: Enable Fsync if you have an Fsync-enabled kernel_
11. Under `System options`, make sure `Prefer system libraries` is `Off`.
12. Run the launcher and install the game. See you in the 'verse!

## Important Information

> During installation of Star Citizen, you may receive an error that Lutris failed to retrieve wine.  We have submitted a request to the Lutris team to fix their install script, which is trying to download an invalid version of the GE runner.  Until then, work around this issue by first installing the runner using the Helper `wine-lutris-ge-6.21-1-x86_64`. Then, navigate to the runner directory (`~/.local/share/lutris/runners/wine`) and rename the directory `wine-lutris-ge-6.21-1-x86_64` to the name that Lutris expects: `lutris-ge-6.21-1-x86_64`.

> If you encounter a white launcher, add the `--use-gl=osmesa` argument in Lutris: `Right click the game->Configure->Game options->Arguments`

> On first launch, the game will stutter with low FPS while shaders are compiled and caches are filled. As you run/fly around and travel to different places, performance will increase.
> This can also occur after updating Star Citizen, your graphics driver, Wine, or DXVK.