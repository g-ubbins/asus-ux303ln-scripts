asus-ux303ln-scripts
====================

Some linux helper scripts for the Asus UX303LN laptop.

After installing Xubuntu on the above laptop, the volume keys and keyboard backlight brightness keys
were non-functional, and I wanted an easier way to switch audio to/from HDMI. By mapping keys to these
scripts (and making other tweaks as below) I got everything working.
These might be useful on other laptops...

Volume keys
-----------
I tried to use amixer to control the volume but gave up. Since pulseaudio is installed, I tried pacmd
and found that I can alter the volume that way.

The volume keys can be mapped to "audio_volume up" / "audio_volume down" / "audio_volume toggle"

Audio output toggle
-------------------
To switch all active sound sources to/from HDMI, a key can be mapped to "audio_output hdmi" / "audio_output analog"

Keyboard backlight brightness
-----------------------------
Inspired by https://help.ubuntu.com/community/AsusZenbookPrime

The brightness keys can be mapped to "keyboard_backlight_brightness up" / "keyboard_backlight_brightness down"

To ensure that any user is able to set the brightness, add this to /etc/rc.local:

chmod a+w /sys/class/leds/asus\:\:kbd_backlight/brightness
