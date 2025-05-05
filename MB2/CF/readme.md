05/05/2025

This folder contain information about a IDE interface that can be used in place of the original MB2 eprom disk.

Zip file is ready for pcb manufacturing.
The bom is simple :
- 2x10 IDE connector
- 1x26 SK7 connector
- 74LS04
- C1 100 nF
- C2 220 µF / 16 V
- one 3x jumper header.

With the jumper you can connect pin 20 of ide connector to +5 V or to 0 V. Some adapter (but not all) can be powered by this way.
Usually pin 20 is removed from most IDE device.
But in case of external power supply of the CF adapter or the IDE Device you use -REMOVE- this jumper. 

This interface has been tested with a Compact Flash boards adapter and with a master and a slave board.

In order to use this board you need a modified monitor (see Monitor).

At boot the CF are automagically detected and initialized. The monitor display what is found.
The detection routine need a timeout so the monitor need time to come on screen especially if there is no Compatc Flash connected.

The eprom and ram disk routines has been removed from the monitor so you cant use these devices.
"Ascii dump" is also removed and "Hex dump" has been improved to have hex and ascii display at the same time.

Master CF is disk $02 and slave CF is disk $03 in RTC table. Put $FF if no disk are used at this place.

For example to have :
- master CF as Flex disk 0
- floppy as Flex disk 1
- slave CF as Flex disk 2
- nothing as Flex disk 4
put 02-00-03-FF into RTC table address $10.

Anyway even if you ask about a CF as a disk somewhere but that the monitor dont detect it at boot it will be not be used.
Accessing this disk under Flex simply give an error.

Slave CF cant be used if no master CF present. 

Last be not least : the Flex disk geometry on the CF is -HARCODED- to 122 tracks / 256 sectors.

You can find here am empty image that can be used with Linux dd to set the disk on CF.
Put it on the DEVICE (fe /dev/sdb), not into a partition.
This image can be used with Michael Evenson FLoppyMaintenance.

Please report any problem you get with this system.
  
Have fun !
Philippe
