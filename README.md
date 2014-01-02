# Lego Mindstorms EV3 hacking

[LegoMindstorms EV3 (31313)](http://www.lego.com/en-us/mindstorms/products/ev3/31313) has been released [recently (2013-09-01)](http://www.lego.com/en-us/mindstorms/news/2013/september/ev3-available-now/), but there are already quite a few projects to play with. 

## What you need
 1. [LegoMindstorms EV3 (31313)](http://www.lego.com/en-us/mindstorms/products/ev3/31313).
 2. Micro SD card 1GB+ ([original instruction]((https://github.com/topikachu/python-ev3)) claims that 2GB is required, I've used 1GB and it works as well).
 3. SD -> Micro SD card adapter.
 4. [Small forceps](http://upload.wikimedia.org/wikipedia/commons/a/a4/Forceps.jpg) to remove Micro SD card from EV3 block.
 5. 6x AA rechargeable batteries.
 6. 2x AAA rechargeable batteries.
 
## Basic Setup (OSX)

Tested on OSX 10.9, should work with previous versions as well based on instructions from [python-ev3](https://github.com/topikachu/python-ev3).

1. Download system image from [Source Forge](http://sourceforge.net/projects/python-ev3/files/python-ev3.img.tar.gz/download) and unzip it:

        $ curl -L http://sourceforge.net/projects/python-ev3/files/python-ev3.img.tar.gz/download | tar xv
2. Copy downloaded image to sd card. First, get the device `<NUMBER>` by inspecting output from:

        $ diskutil list 
        
   _Note: You may need to call `unmountDisk` instead of `unmount` if sd card comes with valid filesystem._
   
        $ sudo diskutil unmount /dev/disk<NUMBER>
        $ sudo dd if=./python-ev3.img of=/dev/rdisk<NUMBER> bs=1m
        $ sudo diskutil eject /dev/disk<NUMER>        
3. Turn off your robot, insert micro sd card and turn it on again.
4. First boot might be time consuming.
5. Connect robot via USB cable.
6. Establish connection:
        
        $ ssh root@10.0.1.1
        
   Password is *password*.
7. Turning off:

        root@10.0.1.1$ shutdown -h now

## Other projects

This is the list of resources / projects I've found so far:

1. Programming EV3 brick with Python: [python-ev3](https://github.com/topikachu/python-ev3).

## Contributions

Are welcome :)

## License 

MIT
