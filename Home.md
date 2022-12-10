# Welcome, Space Penguins!

This wiki is a collection of information on how to run Star Citizen on Linux, as well as our tips and tricks!

🐧 Join us! https://robertsspaceindustries.com/orgs/LUG  

🗨 Discord: https://discord.gg/meCFYPj  
😎 Matrix space: https://matrix.to/#/#SCLUG:matrix.org  

## Contents
* [Quick-Start Guide](https://github.com/starcitizen-lug/information-howtos/wiki/Quick-Start-Guide)
* [Manual Installation](https://github.com/starcitizen-lug/information-howtos/wiki/Manual-Installation)
* [LUG Wine Builds](https://github.com/starcitizen-lug/information-howtos/wiki/Wine-Builds-for-Star-Citizen)
* [Performance Tuning](https://github.com/starcitizen-lug/information-howtos/wiki/Performance-Tuning)
* [Tips and Tricks](https://github.com/starcitizen-lug/information-howtos/wiki/Tips-and-Tricks)
* [Common Issues and Solutions](https://github.com/starcitizen-lug/information-howtos/wiki/Common-Issues-and-Solutions)

## News

> (Oct 17, 2022) DXVK v1.10.2/v1.10.3 may cause a black or transparent screen after launching the game depending on your hardware. If you experience this, try a different DXVK version.

> (Oct 14, 2022) Penguins on rolling release distributions (ie. Arch, Manjaro) are reporting sound issues in-game. The solution is to set `Prefer System Libraries` in Lutris to `ON`.

> (Feb 27, 2022) Glorious Eggroll runners are now based on Proton experimental instead of wine staging. The release version numbers no longer correspond to wine version numbers. The major version number reflects the Proton version it is based on. The numbers after the dashes only reflect GE releases/patches.

> (Feb 12, 2022) **Easy Anti-Cheat is live.** CIG is aware of the problem but there is still no ETA. There are currently no consequences that we are aware of for using the workaround, but CIG has suggested that eventually people will be kicked for tripping EAC. To apply the workaround, use the [LUG Helper](https://github.com/starcitizen-lug/lug-helper).

**Nvidia**

> (Nov 17, 2022) DXVK 2.0 changes the way shaders are handled on some Nvidia cards and may provide better performance than async (see the [release notes](https://github.com/doitsujin/dxvk/releases/tag/v2.0)). If you have worse performance on 2.0, remove the the `DXVK_ASYNC=1` environment variable.

> (Nov 13, 2022) DXVK 2.0 requires Nvidia driver **v510.47.03** or later, but **v520.56.06** or later is recommended.

> (Oct 20, 2022) You may see a popup that your graphics driver is out of date. This is a warning that can be ignored. To remove this warning, disable `DXVK-NVAPI/DLSS` in your Lutris runner options.

> (Jun 11, 2022) NVIDIA users with RTX cards should use [gnusenpai DXVK v1.10.1 or later](https://github.com/gnusenpai/dxvk/releases) to fix the `corrupted size vs. prev_size` error/crash. Can be installed manually or from the LUG helper.

> (March 6, 2022) Driver v495 causes issues for most people. If you have unresolvable performance issues with 510, try 470.
