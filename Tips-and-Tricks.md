## AMD FidelityFX Super Resolution (FSR) upscaling
In the Lutris `Runner options` tab, enable `AMD FidelityFX Super Resolution` or set the environment variable `WINE_FULLSCREEN_FSR=1`. Then, in the Star Citizen graphics settings, set the game to fullscreen and your desired resolution and it will be FSR scaled up. We recommend restarting the game after changing its resolution for better performance.

## Head tracking using Opentrack
At the moment, the simplest method to use Opentrack with Star Citizen is to install the Windows version of Opentrack within Lutris
- Configure it to run from the same wine prefix as Star Citizen
- Select "Freetrack 2.0 enhanced" as the output

## Automatically Disable/Re-Enable Mouse Acceleration
Lutris can automatically toggle on/off a flat mouse acceleration profile with the following configuration

Configure the game within Lutris and go to `System options`. Make sure `Show advanced options` is checked. Add the following to the `Pre-launch script` and `Post-exit script` fields:

**Gnome**

`/usr/bin/sh -c "gsettings set org.gnome.desktop.peripherals.mouse accel-profile flat"`

`/usr/bin/sh -c "gsettings set org.gnome.desktop.peripherals.mouse accel-profile default"`

**KDE**

`/usr/bin/sh -c 'kwriteconfig5 --file "kcminputrc" --group "Mouse" --key "XLbInptAccelProfileFlat" true'`

`/usr/bin/sh -c 'kwriteconfig5 --file "kcminputrc" --group "Mouse" --key "XLbInptAccelProfileFlat" false'`

## Rudder pedals
If your pedals aren't being recognized by Star Citizen, but work on Linux, it may be that it has been classified as something else than rudder pedals. This often happens because there are no buttons, and various OS functions assume it might be an accelerometer or similar.

There are two possible workarounds for this:

1) The following Python script creates a virtual device from the real device, adding a few more capabilities to make Star Citizen not discard it as an invalid device:
https://github.com/beniwtv/evdev-spoof-device

> Note: Consider making a pull request for your device (see quirks section), if there are quirks needed for your device to function.

2) Another solution is to create a Kernel udev rule to change the classification of your device. 

    * Create a file `/etc/udev/rules.d/90-pedals-workaround.rules`.
    * Add this file, changing your vendor and model IDs (can be found by using `lsusb`):

> ACTION=="add|change", KERNEL=="event[0-9]*", ENV{ID_VENDOR_ID}=="044f", ENV{ID_MODEL_ID}=="b679", ENV{ID_INPUT_ACCELEROMETER}="", ENV{ID_INPUT_JOYSTICK}="1", TAG+="uaccess"

> Also consider having the quirk added to systemd by following https://github.com/systemd/systemd/blob/main/hwdb.d/60-input-id.hwdb.

## Suggestions for a good gaming experience
https://robertsspaceindustries.com/spectrum/community/LUG/forum/149/thread/information-how-to-get-a-good-experience-with-star
> Join the org to access Spectrum links: https://robertsspaceindustries.com/orgs/LUG