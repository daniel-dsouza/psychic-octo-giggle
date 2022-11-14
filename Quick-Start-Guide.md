## Installation Steps

1. Install wine-staging (or just the dependencies) on your system following this guide: https://www.gloriouseggroll.tv/how-to-get-out-of-wine-dependency-hell/
2. Install winetricks **v20220411** or newer: https://github.com/Winetricks/winetricks/#installing
3. Install Lutris **v0.5.10.1** or newer: https://lutris.net/downloads/
4. Download our LUG Helper from: https://github.com/starcitizen-lug/lug-helper (distro packages listed [here](https://github.com/starcitizen-lug/lug-helper#installation))
5. Launch the LUG Helper and run the `Pre-flight Check` to optimize your system settings
6. In the LUG Helper, select `Install Star Citizen` and install the launcher to an SSD (we do not recommend an HDD)
7. Run the launcher from Lutris and finish installing the game
8. In the LUG Helper, select `Deploy Easy Anti-Cheat Workaround`
9. In the LUG Helper, select `Manage Lutris Runners`, and install the latest runner from GloriousEggroll (or ask us on our [social channels](https://github.com/starcitizen-lug/information-howtos#socials) which runner is currently recommended)
10. Configure Lutris to use the installed runner. `Right click the game->Configure->Runner Options->Wine version`
11. In the LUG Helper, select `Manage DXVK Versions`. **AMD:** Install the latest dxvk from Sporif Async. **Nvidia:** see our [latest news](https://github.com/starcitizen-lug/information-howtos/wiki#news) for current dxvk recommendations. Follow the instructions [on our wiki](https://github.com/starcitizen-lug/information-howtos/wiki/Performance-Tuning#dxvk-async) to enable it in Lutris
12. Under `System options`, make sure `Prefer system libraries` is `Off`. Only if you have no sound in-game, turn this to `On`
13. Check our [latest news](https://github.com/starcitizen-lug/information-howtos/wiki#news) for important Nvidia gpu driver issues, necessary workarounds, and currently recommended runner/DXVK versions
14. Run the launcher again and start the game. See you in the 'verse!

## Video Guide
Video guides of the above are available for [AMD](https://www.youtube.com/watch?v=cHGtwIH5ocI) and [Nvidia](https://www.youtube.com/watch?v=QVVPv12RGtk) by Grumpy

## Important Information
> Questions or Problems? Ask for help in one of our [social channels](https://github.com/starcitizen-lug/information-howtos#socials)!

> On first launch, the game will stutter with low FPS while shaders are compiled and caches are filled. As you run/fly around and travel to different places, performance will increase.
> This can also occur after updating Star Citizen, your graphics driver, Wine, or DXVK.