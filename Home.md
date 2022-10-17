# Welcome, Space Penguins!

This wiki is a collection of information on how to run Star Citizen on Linux, as well as our tips and tricks!

Join us! https://robertsspaceindustries.com/orgs/LUG  

Discord: https://discord.gg/meCFYPj  
Matrix space: https://matrix.to/#/#SCLUG:matrix.org  

## Contents
* [Quick-Start Guide](https://github.com/starcitizen-lug/information-howtos/wiki/Quick-Start-Guide)
* [Manual Installation](https://github.com/starcitizen-lug/information-howtos/wiki/Manual-Installation)
* [LUG Wine Builds](https://github.com/starcitizen-lug/information-howtos/wiki/Wine-Builds-for-Star-Citizen)
* [Performance Tuning](https://github.com/starcitizen-lug/information-howtos/wiki/Performance-Tuning)
* [Tips and Tricks](https://github.com/starcitizen-lug/information-howtos/wiki/Tips-and-Tricks)
* [Common Issues and Solutions](https://github.com/starcitizen-lug/information-howtos/wiki/Common-Issues-and-Solutions)

## News

> (Oct 14, 2022) Penguins on rolling release distributions (ie. Arch, Manjaro) are reporting sound issues in-game. The solution is to set `Prefer System Libraries` in Lutris to `ON`.

> (Jun 11, 2022) **Note to Nvidia users:** NVIDIA users Should use [gnusenpai DXVK v1.10.1 or later](https://github.com/gnusenpai/dxvk/releases) to fix the `corrupted size vs. prev_size` error. Can be installed manually or from the LUG helper.

> (May 22, 2022) **SC 3.17.1** currently requires a Wine patch to play. Work is going on to add that to upstream Wine, but in the meantime, you can build with this [patch](https://build.opensuse.org/package/view_file/home:ngh/wine/threadpowerthrottlingstate.patch?expand=1), or use one of the pre-compiled versions from [GloriousEggroll](https://github.com/GloriousEggroll/wine-ge-custom/releases/tag/GE-Proton7-15-SC) or  [RawFox](https://github.com/starcitizen-lug/raw-wine/releases/tag/7.12).

> (March 6, 2022) **Note to Nvidia users:** Driver v495 causes issues for most people. If you have unresolvable performance issues with 510, try 470.

> (Feb 27, 2022) Glorious Eggroll runners are now based on Proton experimental instead of wine staging. The release version numbers no longer correspond to wine version numbers. The major version number reflects the Proton version it is based on. The numbers after the dashes only reflect GE releases/patches.

> (Feb 12, 2022) **Easy Anti-Cheat is live.** CIG is aware of the problem but there is still no ETA. There are currently no consequences that we are aware of for using the workaround, but CIG has said that eventually people will be kicked for tripping EAC. Ask in any of our social channels or use the LUG Helper.