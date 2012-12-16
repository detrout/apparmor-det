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

Spectrum2
---------

This is fully my own creation. 

I'm not sure how one should share common features between related profiles.

The three spectrum modules all want access to the log directory and the 
configuration files for instance. 

There were various features spectrum wanted access to to manage its subprocesses.
/proc/{pid}/statm r, and nice & sys block block_suspend which I allowed.

It also wanted ptrace which bothered me, so I didn't enable that capability.

