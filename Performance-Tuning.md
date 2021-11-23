## Nvidia users

By default Nvidia has a combined cache for all games. As the cache fills up from other games, Star Citizen's shaders may get deleted leading to poor FPS. We recommend giving SC its own persistent cache by adding the following environment variables:

```
__GL_SHADER_DISK_CACHE=true
__GL_SHADER_DISK_CACHE_PATH="/path/you/want/for/your/cache"  (example: /home/myuser/.cache/sccache)
__GL_SHADER_DISK_CACHE_SKIP_CLEANUP=true
```

## AMD users

If you have an AMD GPU, you need to enable the new shader compiler, called ACO. This will make the stuttering when compiling shaders for the first time a lot better compared to LLVM. It also fixes the crash you get when walking down the stairs at Port Olisar or when approaching the elevator at Area 18.
_As of Mesa v20.2.0, RADV uses ACO by default._

To enable ACO if it is not already enabled by default, you need to add **RADV_PERFTEST=aco** to your environment variables. With Lutris this is easy, you can set it for the game in the settings for the game in Lutris, under the "System options" tab, where you'll find an option for it. If you run a manual Wine install, add/run "export RADV_PERFTEST=aco" in your shell/script you use to run the game.

## Special LUG Wine Builds
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