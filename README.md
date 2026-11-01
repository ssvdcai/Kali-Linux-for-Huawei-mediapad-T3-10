# Kali-Linux-for-Huawei-mediapad-T3-10
linux ported via postmarket kernel 7.1.x with patches for huawei mediapad t3 10 agassi

!!! I am not an official guy that makes this kind of things, I am an 15 year old... so please consider that if it does not work. If you would like, send me any issue on xda, but  also consider that I have school and other stuff... I do this as a hobby.

Added working sound, not perfect , but it works. 
it uses kernel 7.1 by postmarket with ralink modules and added support for RTL8812AU 

I configured the .dtb in kernel to support host mode usb, so adapters will work. 

Due to the changes at usb, usb networking does not work.

Look please at /usr/local/bin for audio scripts, if you want to improve it.

Freetube volume is weird... it chuckles like a radio, use vacuumtube... it comes pre-installed.

If wifi does not work, look into the "cust" partition on your tablet to see the .ko.zst files necesarry. 

**I have not tested it for AGS-L09, only for AGS-W09 , 2 GB RAM and 16 storage.**

A thing I strongly recommend... *[but risky]* is to shrink the system partition for extra storage, make it 1 MB, then put it where it should start in the partition map.

Before every change, please create an edl backup with "edl rl . --loader=firehose.mbn"

At boot, it sometimes does not load the touch  module... just reboot it holding the power button, it should fix it.

IN THE RIGHT CORNER OF THE PANEL, YOU HAVE AN ICON NAMED ROTATE, IT ROTATES THE SCREEN ALONG WITH THE TOUCH ON THE LEFT SIDE.


GPU is acting weirdly on firefox and everything ... If you could fix it and send me a report of how I can fix it... you are welcome. Everything uses software rendering.

USER PASSWORD : kali

**DOWNLOAD USERDATA: https://mega.nz/file/THBjwJYb#saguvIMVdS_VmLFzrKHUHLAPEDQCPdP45WMJ5iUP_9s**
After downloading the userdata_sparse flash it with fastboot on userdata partition, so lk2nd will see it

!!!ONLY WORKS AFTER fastboot flash boot lk2nd_agassi.img 
     ( if it does not boot, try flashing lk2nd in recovery parition also )
