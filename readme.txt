event toolset
=============

little toolset for logging information from /dev/input/event* devices.
for the sniffer i first opened the device by myself and parsed it, it worked. but worked much
better with the evdev library.
please be aware that root privs are needed.

prerequisites
-------------
https://python-evdev.readthedocs.org/en/latest/
pip2 install evdev

map_devices.py
--------------
just print out information about all event devices on your system.
# python2 map_devices.py 
[...]
------------------------------------------------------------
[/dev/input/event14]
Video Bus
bus: 0019, vendor 0000, product 0006, version 0000
LNXVIDEO/video/input0
------------------------------------------------------------
[/dev/input/event15]
SynPS/2 Synaptics TouchPad
bus: 0011, vendor 0002, product 0007, version 01b1
isa0060/serio1/input0
------------------------------------------------------------
[...]

evdev_sniffer.py
----------------
keyboard sniffer using the evdev library. write per default the logged data to .keylog ;)

gen_keymap.sh
-------------
simple shellscript generating keymap for event_sniffer.py
event_sniffer is not using the evdev library, so it is more independent.

event_sniffer.py
----------------
well like evdev_sniffer but without the evdev_library :)

thanks
------
thanks goes out to stealth for pointing me to this neat trick, he implemented back then via injectso.
(http://stealth.openwall.net/local/injectso-0.52.tgz)

author
------
dash@hack4.org
