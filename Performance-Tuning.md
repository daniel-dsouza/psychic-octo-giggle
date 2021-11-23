## LUG Helper
We have a helper script which can help you manage and optimize Star Citizen on Linux. It can check/set recommended settings such as vm.max_map_count and the system's open file descriptors limit, manage Lutris runners and DXVK versions, delete your Star Citizen USER directory while preserving keybinds, and delete shaders or dxvk cache for troubleshooting purposes. It can be downloaded from:

https://github.com/starcitizen-lug/lug-helper

## Nvidia Cache

By default Nvidia has a combined cache for all games. As the cache fills up from other games, Star Citizen's shaders may get deleted leading to poor FPS. We recommend giving SC its own persistent cache by adding the following environment variables:

```
__GL_SHADER_DISK_CACHE=true
__GL_SHADER_DISK_CACHE_PATH="/path/you/want/for/your/cache"  (example: /home/myuser/.cache/sccache)
__GL_SHADER_DISK_CACHE_SKIP_CLEANUP=true
```

## AMD ACO Shader Compiler

If you have an AMD GPU, you need to enable the new shader compiler, called ACO. This will make the stuttering when compiling shaders for the first time a lot better compared to LLVM. It also fixes the crash you get when walking down the stairs at Port Olisar or when approaching the elevator at Area 18.
_As of Mesa v20.2.0, RADV uses ACO by default._

To enable ACO if it is not already enabled by default, you need to add `RADV_PERFTEST=aco` to your environment variables. With Lutris this is easy, you can set it for the game in the settings for the game in Lutris, under the `System options` tab, where you'll find an option for it. If you run a manual Wine install, add/run `export RADV_PERFTEST=aco` in your shell/script you use to run the game.