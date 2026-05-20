# DIY TagConnect TC2050

> This is a work in progress.
> I would not recommend to use the Rev1.0 ([details below](#notes-on-rev10))\
> Will update this repo with a Rev1.1 and a leg-less version once I find some time.

Want to use the TagConnect connector for flashing and debugging on your PCB, but don't have a TC2050 cable, nor a compatible debug device (like a JLink)? 

That's exactly the issue I ran into. Therefore I designed a connector usable with the TagConnect TC2050 footprint. (I plan to use this connector with a Pico flasher.)

![](./3D-Model/DIYTC2050.png)

## How it works

The 10 pogo-pins are soldered onto a tiny PCB. The larger holes are for soldering the cables of your debug device onto the PCB.

The 3D printed housing acts as a guide for the pogo pins and inserts into the target PCB's TC2050 footprint, just like the real connector.

## Requirements

- a 3D printer for printing the housing (`3D-Model/DIYTC2050_Housing.stl`) and the soldering spacer (`3D-Model/DIYTC2050_SolderingSpacer.stl`) (0.2mm nozzle or SLA printer recommended)
- the PCB breakout board (gerber for JLCPCB in `Gerber/DIYTC2050.zip` - KiCad files in `DIYTC2050/`)
- 10x P50-B1 pogo pins (0.68mm diameter, 16mm length) ([Amazon](https://amzn.eu/d/0aM7f1Ir))
- a threaded insert + screw for screwing the PCB onto the connector housing (M4 recommended)

## Assembly

1. Insert the pogo pins (with the spring part facing down) into the soldering spacer
2. Put the PCB onto the soldering spacer and solder the pins to the pcb
3. Solder your debug wires to the PCB
4. Insert the threaded insert into the connector housing
5. Screw the PCB onto the housing

## Notes
- the screw connection from PCB to housing is not great, but I will try it like this for now
- the PCB only supports the SWD pinout - i may add a JTAG version (or combine both) in the future
- the schematic and footprint for the TC2050 (with correct pinout) can be found in `Symbols/TC2050/`

## Notes on Rev1.0

A few notes before I describe my assembly journey:

Printing the housing and the spacer with a 0.4mm nozzle did not work great. Even after adjusting slicer settings the holes for the pogo pins were clogged. To fix this I printed it with a 0.2mm nozzle (with PLA). I reckon a SLA printer would work as well.
I will probably get rid of the legs as well as they are very fragile, but we will see.

Making the holes in the PCB large enough for soldering the cables directly to it it probably not the way to go. I will rework this PCB soon to feature a pin header, where one can connect jumper cables.

### First Assembly

I assembled the connected, as described in [Assembly](#assembly). Here is how it went:

First things first I soldered the pogo pins to the PCB using the spacer. This worked great. The spacer melted in the process, as it was printed with PLA. Make sure to remove the spacer from the pins while it's still hot, otherwise you may not be able to easily remove it.

![](./Pictures/26-05-14%2019-43-36%202745.jpg)
![](./Pictures/26-05-14%2019-51-22%202746.jpg)

After that I inserted the heat insert into the housing. Make sure to not completely melt it. I luckily was able to bend it back into shape before it cooled down. Therefore the damage wasn't that bad.

![](./Pictures/26-05-14%2019-53-35%202747.jpg)
![](./Pictures/26-05-14%2019-55-46%202748.jpg)

After screwing the PCB to the housing, I decided it would be nicer to solder pin headers to it instead of directly soldering the cables onto it. Therefore it looks a bit scuffed^^
![](./Pictures/26-05-14%2020-17-01%202750.jpg)
