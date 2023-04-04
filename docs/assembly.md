# Assembling the modified parts

Please read the entire instructions before starting the assembly, so you know what's coming. Also, 
read the entirety of each step again before starting that step.

## Step 1: Assemble the bottom PCB

The bottom PCB is the bigger one that is not assembled. 

Solder one of the right-angled connectors onto it. Make sure it's on the top side. When you hold the PCB on the bottom
of the printed sensor housing, the connector should fit into the small space that is there for it.

Now, use a multimeter to check that there are no shorts between the connector contacts. **Always do this when this
guide tells you to**, or you **will** inevitably run into trouble fixing it if you find a short later.

Cut off 3-pin piece of the 2.54mm pitch pin header strip and solder it on as well.

Repeat for all the bottom PCBs.

## Step 2: Assemble the control PCB.

The control PCB is the biggest one that is already mostly assembled.

Solder the ESP-S3-32S module in the place where it belongs. Make sure all the contacts are connected and that there are
no shorts. Don't worry about the exposed contacts in the middle of the part. This is just in case someone smart finds
a way to put the original Espressif module here (if that's you, my head is off to you for presumably having a reflow
oven, also thanks for reading this guide even though you probably don't need it).

Populate the BUTTONS and JOYSTICK pin header slots. The PROG/UART pin header slot can be populated as well, but you can
skip it if you don't feel like it.

Now, take one of the cables that connect to the connectors. Plug it into one of your bottom PCBs. Check which wire color
corresponds to which of the labels (5V, SIN, COS, etc…) on the board. 

Now, put in one of the connectors without soldering it on yet. Make sure that if you plugged the cable in it, the colors match the labels here in
the same way. This is to check if the connector on the end of your cable is the right way around. If the labels
**don't** match, they should match if you put the connector on the other side of the PCB. Solder it on the correct side,
then solder on all the other connectors the same way.

Check for 

Repeat for all control PCBs.

## Step 3: Attach the top PCB

Take one of the top PCBs (kinda L-shaped) and try to fit it into its slot. Note how it covers the hole for the splay
hall effect sensor and the +, - and S labels next to the 3 holes for the legs of the hall effect sensor. 

Remove the PCB and stick the hall sensor into the hole in the right orientation. If needed, check for the pinout of the
sensor online. Make sure the sensor body does not stick out of the other side. Fit the PCB on top of it again.

Do not solder on the sensor yet. Instead, cut off the sensor legs so that a bit of them are still sticking out. You need
to cut off 13-14 mm at least. Keep these, you will need them. (If this is the second time you are doing this, you can
clip the sensor legs later because you should have enough leg clipping lying around.)

Stick the legs into the 3 other holes in the PCB that will connect the top PCB to the bottom pcb. Solder them in place.
If needed, you can remove the PCB for this.

Use your multimeter to check that there are no shorts between the 3 leads.

Put the PCB back if you removed it. Now, solder the sensor legs in place. Make sure the sensor is facing the right way
and is not sticking out on the bottom.

Now, use your multimeter to again check that there are no shorts between the 3 leads. You can measure it at the 
connector or directly at the sensor. Don't worry if your multimeter now says the leads are connected with some 
resistance. This is normal for the hall sensor. As long as there is not nearly zero resistance, everything is fine. If 
you want to be extra sure, measure the resistance between the legs of a hall sensor directly and compare.

Use one of the M2 screws to fix the PCB in place. 

## Step 4: Attach the bottom PCB

Use the same strategy as for the top PCB to determine the right orientation for the sin/cos hall sensors. Fit the
bottom PCB onto them, and also onto the leads that come of your top PCB that will connect it to the bottom PCB.

Solder on each sensor seperately as well as the connector to the top PCB. Then, use your multimeter to check for shorts
again. For completeness's sake, you can also check for this at the 6 pin connector.

Now, use two of the M2 screws to fix the PCB in place.

Repeat Step 3 and Step 4 for every finger module. 

## Step 5: Finger module assembly

Follow the original Prototype 5 instructions to assemble the finger modules. In the end, plug in the servo into the pin 
header. Note that the brown wire should connect to the pin labeled GND. 

Congratulations, your finger modules are ready!

## Step 6: Final assembly

Mount all the finger modules to the hand mount.

Attach your tracker to the tracker mount. Mount the control PCB to the tracker mount using two M2 screws.

Plug all the wires into the finger modules and connect them to the PCB. One of the wires can fit through the hole in
the tracker mount. 

Congratulations, you are done!
