## Runners
Some of our members build wine runners tailored specifically for Star Citizen.

### Molotov
Contains a selection of wine-staging patches.  Often contain experimental patches and solutions for certain problems, i.e. joystick axis fixes.
Mol is using Docker containers to build the runners.
https://github.com/snatella/wine-runner-sc/releases

### Raw_FoX
Full wine-staging builds with a focus on stability and runability. Best balance between performance and safety. Tested to work for most people.
https://github.com/rawfoxDE/raw-wine/releases

## Installation
If you use Lutris, you can use the [LUG Helper](https://github.com/starcitizen-lug/lug-helper) to manage your wine runners or manually install them:

* Put the runner download in `~/.local/share/lutris/runners/wine/` and restart Lutris
* In Lutris game configuration select the extracted runner from the pulldown menu

If you do not use Lutris, you can use the Wine build as follows:

* Put the download in a directory of your choice, for example, `~/Downloads/lug-sc-wine`
* Use `~/Downloads/your-runner/bin/wine` as Wine executable for running the game / installer.

## Further reading
For more information about runners, see:

https://robertsspaceindustries.com/spectrum/community/LUG/forum/149/thread/information-how-to-deal-with-the-lutris-runners
> Join the org to access Spectrum links: https://robertsspaceindustries.com/orgs/LUG