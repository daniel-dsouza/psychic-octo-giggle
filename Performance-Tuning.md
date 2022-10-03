## LUG Helper
We have a helper script which can help you manage and optimize Star Citizen on Linux. It can check/set recommended settings such as vm.max_map_count and the system's open file descriptors limit, manage Lutris runners and DXVK versions, delete your Star Citizen USER directory while preserving keybinds, and delete shaders or dxvk cache for troubleshooting purposes. It can be downloaded from:

https://github.com/starcitizen-lug/lug-helper

## DXVK Async
Using an async DXVK can greatly reduce stuttering. We recommend https://github.com/Sporif/dxvk-async/  
You can manually download it or use the Helper to automatically install it for Lutris. After downloading, be sure to set the environment variable `DXVK_ASYNC=1` and enable the downloaded version in the Lutris runner options.
1. `Right click the game->Configure->System options->Environment variables`. Add `DXVK_ASYNC` as the key and `1` as the value.
2. `Right click the game->Configure->Runner Options`. Check `Show advanced options` to unhide `DXVK version`.
3. In `DXVK version`, select `Manual` then overwrite it with the folder name of the downloaded dxvk (ie. _dxvk-async-1.9.4_)

![](https://matrix-client.matrix.org/_matrix/media/r0/download/matrix.org/wQRsUySnKmchQWyZrmoZFDnJ)

## Nvidia Cache

By default Nvidia has a combined cache for all games. As the cache fills up from other games, Star Citizen's shaders may get deleted leading to poor FPS. We recommend giving SC its own persistent cache by adding the following environment variables:

```
__GL_SHADER_DISK_CACHE=true
__GL_SHADER_DISK_CACHE_PATH="/path/you/want/for/your/cache"  (example: /home/myuser/.cache/sccache)
__GL_SHADER_DISK_CACHE_SKIP_CLEANUP=true
```

If you use Lutris, these environment variables can be added here:

`Right click the game->Configure->System options->Environment variables`

![](https://matrix-client.matrix.org/_matrix/media/r0/download/xndr.de/AwspONZSbLKcXCCkBojwyIYT)

## Game Settings

The following game settings can help improve framerates:

- Set `Quality` to `High`. Lower settings are not recommended as it will tax your CPU more. Set to `Very High` to offload more work from your CPU to your GPU.
- Set `Planet Volumetric Clouds` to `Medium`
- Set `Scattered Object Distance` to `Low`
- Set `Motion Blur` to `Off`
- Set `Sharpening` to `100`

## Feral GameMode

Gamemode can help improve performance by applying OS-level performance tweaks as the game is launched. Search for `gamemode` in your Distro's repos. Once installed, Lutris has a toggle for `Enable Feral GameMode` under `System options`. It defaults to ON if it detects gamemode is installed.

## Fsync

An fsync-enabled Kernel can help improve smoothness while shaders are being compiled in the game. Enable fsync in Lutris under Runner Options.