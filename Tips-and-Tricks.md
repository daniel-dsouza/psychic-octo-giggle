## Automatically Disable/Re-Enable Mouse Acceleration
If you use Gnome, Lutris can automatically set a flat mouse acceleration profile with the following configuration:
* Configure the game within Lutris and go to `System options`. Make sure `Show advanced options` is checked. Add the following to the `Pre-launch script` field:

`/usr/bin/sh -c "gsettings set org.gnome.desktop.peripherals.mouse accel-profile flat"`

* And add the following to the `Post-exit script` field:

`/usr/bin/sh -c "gsettings set org.gnome.desktop.peripherals.mouse accel-profile default"`