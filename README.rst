AppArmor DET
============

I need some apparmor profiles, I thought I should make them available.

Skype
-----

I found a skype profile at
http://eternalwalkabout.wordpress.com/2012/02/01/ubuntu-11-10-skype-apparmor-profile/
Unsurprisingly it doesn't work all that well with ubuntu 12.10

I gave skype access to:

  * dbus-sessions
  * I gave it memory map permissions to /usr/share/fonts/ and its subdirectories
  * read access to /sys/devices/system/cpu/
  * mostly so it can read cpu*/cpufreq/scaling_{cur,max}_freq
  * Ability to run pulseaudio with Px "Discrete profile execute mode 
    with scrubbing the evironment
  * Added .config/Skype/** to the directories skype can read/write

