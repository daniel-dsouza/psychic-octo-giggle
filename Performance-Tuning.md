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
