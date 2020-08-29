Cherry Blossom Numpad
=====

![](img/numpad.jpg)

A custom DIY numpad. See the build process and it in action [here](https://youtu.be/7neqXtf0uJI).

Features:
 - RGB Backlighting with APA102
 - Encoder side wheel with push button
 - Support for 17 or 20 key layouts
 - Gesture sensor (APDS-9960)
 - QMK powered

The APDS-9960 gesture sensor can detect proximity, brightness, color, or gestures. Gestures consist of up, down, left, right, close and far. Using the gesture detection is currently a little finicky because if there is a gesture being performed over the sensor (or really any movement over the sensor) the numpad is unresponsive to all button inputs.

PCB gerbers, schematic, and BOM are in the `pcb` folder. The BOM has the Mouser numbers for the parts I ordered (The unfilled in parts numbers are not there because I had those on hand. The USB-C connector came from eBay; look for the ones that only have a single row of pins. The six pin programming header is only needed if you somehow are unable to program over USB.).

A couple of things to look out for when building this:
 - The footprint for the diodes are pretty much exact fits for the diode, which makes soldering by hand rather difficult (reflow is okay). If I make a revision this will be updated.
 - The USB-C connector being on top means that if you solder the switches in the plate flush to the PCB, there may not be enough clearance between the USB cable you use and the plate. I soldered the switches so the legs of the switches barely pop out of the PCB holes. A new revision would have the USB-C connector on the bottom of the PCB.
 - You need small jumper wires when soldering the floating legs of the encoder to the PCB. A revision will move the pads to the edge of the PCB for direct soldering.
 - The case may need some changes to the USB-C connector hole. It seems to work for the prototypes I made, but I also had some strange manufacturing issues specific to my process.
 - I don't have the time right now to make the changes for the revision and test it.

One day if I get the time and there is interest I could put together a kit.

A 3D model of the case and plate without the gesture sensor hole is in the model folder called `numpad_nogesture.step`. If you want the hole for the gesture sensor, use the model `numpad_gesture.step`. The body thicknesses are slightly different because they came from different models where I had different material thicknesses set for CNC operations.

The firmware for the numpad is under my personal fork of the QMK firmware.