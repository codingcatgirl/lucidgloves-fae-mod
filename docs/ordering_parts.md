# Ordering the parts needed

## Parts needed

For each of these, remember that having 1-2 to spare can be very useful.

* 1× (per glove) **ESP-S3-32S by Ai-thinker** ([AliExpress](https://www.aliexpress.com/item/1005004078472526.html))
  * If you order it somewhere else, make sure it definitely is the **S3** version by **Ai-thinker**, and **NOT an 
    ESP32-S3-WROOM** module from Espressif. That one has soldering pads on the bottom, so you cannot hand solder it.
* 10× (per glove) **JST 6 pin 1.25mm pitch right angle THT connector** ([AliExpress](https://www.aliexpress.com/item/1005004374200185.html))
  * Make sure you select the **right angle version** (called “curved needle” in the linked product) and 
    **6 pin version** (called “6P” in the linked product).
  * This seems to actually not be a connector from JST, but for some reason sellers on Aliexpress call it that anyway.
  * In theory, you can select other right-angled connectors with 6 pins and 1.25mm, but if you do make sure you are
    ordering the right cables for it as well.
  * (If you opt to have JLCPCB assemble these for you (see below), you will only need 5 of these per glove.)
* 5× (per glove) **JST 6pin 1.25mm pitch cable 10cm** ([AliExpress](https://www.aliexpress.com/item/1005002531804129.html)) 
  * Make sure you select the **6 pin versiom** (called “6P” in the linked product) and **10cm** (15cm is fine too).
* **2.54mm pitch pin headers** ([AliExpress](https://www.aliexpress.com/item/32758380907.html))
  * They are used to more easily connect buttons, joysticks and (should you ever need it) a programmer
    using jumpers. In theory, most of them are optional, but you need 3 pins per finger to connect the servo.
  * The AliExpress link here is merely an example but those will be plenty for even 10 gloves and more. You can find
    these everywhere and might even have some laying around still. Per glove you will need 38 pins, unless you chose to
    leave out some.
  * (If you opt to have JLCPCB assemble these for you (see below), you will only need 15 pins per glove.)
* 17× (per glove) **DIN912 M2×5 screws** ([AliExpress](https://www.aliexpress.com/item/759266313.html))
  * Similar screw will do. 4mm or 6mm will work as well.
  * Strictly speaking these are optional if you like hot gluing things.

You will **not** need the following parts from the original gloves: 

* ESP32-WROOM-32(U)
* CD74HC4067 Multiplexer

## PCBs

This is a guide on how to order the PCBs from JLCPCB. You can of course order them anywhere else if you want.

There are 3 different PCB that you will need to order. We start with the control PCB.

Create an account/sign into [JLCPCB.com](JLCPCB.com). Click on “Order now”. On the first page, do the following:

* Download [control_pcb.zip](../pcb/control_pcb.zip), and upload it usin the “Add gerber file” button.
* Set the “PCB Color” to one you like.
* Set the “Surface Finish” to LeadFree HASL, unless you are absolutely fine with lead. ENIG is also then option,
  very fancy but also very expensive. For some combinations of color and surface finish a warning will pop up and it
  will add a significant Special Process Fee. If that happens, you probably want to choose another color. 
* Set “Remove Order Number” to “Specify a location”.
* Switch on "PCB Assembly".
* Double check that “PCBA Type” is set to “Economic“. If you can't select Economic, you need to choose another 
  combination of PCB Color and Surface finish.
* Click “Confirm”.

Click next until you reach the Upload for the BOM and CPL files.

* Download [the BOM file](../pcb/control_pcb_bom.csv) and [the CPL file](../pcb/control_pcb-top-pos.csv) and upload
  them respectively.
* Click “Process BOM & CPL”.

You are now on the page where you can review the parts that will be put in the PCB.

* Parts that are marked as “Extended” instead of “Basic” cost an extra fee. You can save money by leaving out some
  of them and acquiring and soldering them on yourself. 
  * This guide recommends and assumes that you leave out the pin headers and connectors, get those from AliExpress (see 
    below) and solder them on yourself because they are easy to solder and having them assembled would cost $10 more.
  * For this, untick the checkboxes of the Lines that say FINGER1, FINGER2, FINGER3, FINGER4, FINGER5, UART/PROG,
    JOYSTICK and BUTTONS. In total, you should unselect 8 checkboxes.
  * You can decide to leave these parts in and have them assembled if it's worth the additional cost to you. The
    selected connectors should fit the cables, but it has not been tested.
* Click “Next”. There will be a warning telling you that there is one part that can only be assembled using Standard
  assembly. 
  * This is the ESP chip. This part cannot be assembled using Economic Assembly due to temperature restrictions. 
    In the past, this has not been an issue. Apparently it is possible to contact JLCPCB support and ask them to unlock
    this part for Economc Assembly. This guide recommends and assumes that you will get this part from AliExpress (see
    below) and solder it yourself. 
  * Choose “Do not place this part”. Do **not** switch to Standard PCBA.
* Click “Next” again. There will be another, similar warning, that there are some unselected parts. 
  * Again, choose “Do not place”.

You are now on a page that shows you a preview of the assembly. 

* Some parts will not be in the right position. This is fine since this is only a preview and JLCPCB will correct the
  placement after you placed your order.
* Click “Next”.

You are now on a summary page.

* You should see a total price of around $27. If not, double check that you did everything right.
* For Product Description, you have to select what applies, usually DIY should do.
* Click “Save to Cart”.

Repeat these steps with [top_pcb.zip](../pcb/top_pcb.zip) and [bottom_pcb.zip](../pcb/bottom_pcb.zip), but:

* Make sure that you select the right quantity. You need one of each per finger. 
* Do not set “Remove Order Number”.
* Do not enable assembly.

You can experiment with the quantities of the PCBs in your cart to see how it affects the price. 

* Don't be confused that the top and bottom PCBs don't have the same price in your cart, this is due to special offers 
  that apply only once per order.
* If you make two gloves, it could still be useful to order 15 top and bottom PCBs each so you have a few spares, 
  if it's worth the cost to you.
* You can, in theory, also ask them to only assemble 2 control PCBs instead of all 5. This guide does not recommend 
  this, as it barely saves you any money, and it's good to have spare PCBs just in case.

If you are happy, go to checkout. Pay attention to the following two things:

* On the payment page, there will be a select the $9 coupon for SMT Assembly. Don't forget to select that one.
* There's an extra fee if you use PayPal.

Congratulatios, you're done with the PCBs!
