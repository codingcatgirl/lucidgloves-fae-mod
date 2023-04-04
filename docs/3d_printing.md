# Ordering the parts needed

## Modified Sensor Housing

* Download  [Modified Sensor Housing STL](../stl/SensorHousing_v5.9_FaeMod_v1.0.stl).
* No supports or anything similar needed. 
* In order for bridging helpers to work correctly, you need to print a layer height of 0.15mm or lower and 3 outer
  perimeters or more. 
* At that point, infill won't matter and can be pretty low.
* After printing, remove the two tiny bridges at the end of the module holding up the "lip".

## New Tracker Mount

* Download [New Tracker Mount STL](../stl/TrackerMount_FaeMod_v1.0.stl).
* No supports or anything similar needed.
* In order for bridging helpers to work correctly, you need to print a layer height of 0.2mm or lower.
* 2-3 perimeters should be enough.
* Infill doesn't matter.

## Two-Material flexible version of the rigid mount

You will need flexible filament for this (duh). For example, this was tested with Fiberlogy Fiberflex 40D. 

* Download [the rigid part](../stl/RigidMount_Splay_v3_FaeMod_Rigid_v1.0.stl) and 
  [the flexible part](../stl/RigidMount_Splay_v3_FaeMod_Flex_v1.0.stl) of the modified rigid mount.
* There are many guides online on how to print multi material if your printer has only one nozzle and you can look 
  for more detailed instructions for your slicer/printer. However, here's a brief summary:
  * Tell your slicer that your printer has two hot ends (even if it doesn't). 
  * Import the two STLs into your slicer, make sure it detects it as two parts of the same object for multi material
    printing.
  * Set the filaments correctly for the flexible and rigid part.
  * Make sure your printer supports `M600` or a similar print pause/filament change G-Code command.
  * Set `M600` (or whatever command your printer understands) as the custom Filament Change/Tool Change G-Code.
    In PrusaSlicer/SuperSlicer, you find this in the Custom G-Code section of your Printer profile. In Cure, there
    is an Extension called “Post Processing” that you can use to add a custom G-Code script.
* Set the layer height to 0.25mm for the bottom 1mm or the entire print. You can set it lower, but then you'll have
  to change the filament more often.
* If you have done it correctly, there should only be 4 manual filament changes for the entire print.
* No supports needed, infill doesn't matter, 2-3 perimeters recommended.
* Good luck!
