Design files for the new version of the MB2 PCB created by Philippe Roehr 
<ph-roehr@orange.fr>

Today (29/12/2021) the main pcb and eprom 27C256+AT28C256 has been put in production. These files will not be updated.

Gerber_main_41256.zip       Gerber files from main pcb
Gerber_27256                Gerber files for 27256 eprom disk pcb
Gerber_27256_28C256         Gerber files for 27256 or AT28C256 eprom disk pcb without 27526 programming capability

This PCB is ready for double side floppy and 256 kb video ram.

MODIFICATIONS :

J1 and J2 are for dual side floppy fonction (R57 is the pull up resistor 1 kR). Leave J1 open and populate J2 for ds floppy. If you want use an old version of
MON09 with step rate on PB6 then leave J2 open and populate J1.

J3 is for connecting SK1/17 to SK2/15 or SK1/17 to IC19/18 or both...
See here connectors pinout : http://www.retro.co.za/6809/microbox/index.html. Thanks Wouter to put that online !

J4 and J5 can invert Hsync and Vsync polarity (choice between Q or ~Q output) on SK8 connector. Normal position for composite video (SK9) use is J4 2-3 and J5 1-2.
If you invert Hsync and / or Vsync only SK8 can be used. Video out SK9 will not works correctly.

On SK8 +5V and PCLK has been added in case of.

IC69 (74LS257) is for using 41256 dram on IC47 to IC62, not required if you use 4164 dram.

Z2 and R58 are for increasing rtc disable speed at power off, protecting stored datas against crazy bus...
Use 4.3 V zener + 220 R resistor.

There is also a jumper to close for clearing the rtc (normally open).

Philippe
