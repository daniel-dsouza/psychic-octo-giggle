## Automatically Disable/Re-Enable Mouse Acceleration
If you use Gnome, Lutris can automatically set a flat mouse acceleration profile with the following configuration:
* Configure the game within Lutris and go to `System options`. Make sure `Show advanced options` is checked. Add the following to the `Pre-launch script` field:

`/usr/bin/sh -c "gsettings set org.gnome.desktop.peripherals.mouse accel-profile flat"`

* And add the following to the `Post-exit script` field:

`/usr/bin/sh -c "gsettings set org.gnome.desktop.peripherals.mouse accel-profile default"`

## Suggestions for a good gaming experience
https://robertsspaceindustries.com/spectrum/community/LUG/forum/149/thread/information-how-to-get-a-good-experience-with-star
> Join the org to access Spectrum links: https://robertsspaceindustries.com/orgs/LUG