## MT.Strobic

![MT.Strobic v2.0](/img/1.png)
<p align="center">Picture 1 - MT.Strobic</p>

MT.Strobic developed by me, when I studied on first semester of fourth year bachelor program at the Mechatronics Department (ITMO University, Saint-Petersburg, Russia).

MT.Strobic is just one more DIY stroboscopic display which you can find in the internet. It can be used just for fun or in more specific way. For example, as backpack flasher when you walk on unlit road in night time.

It’s not the easiest guide how to build this device, but I think, every high school schoolboy, who has electronics as a hobby and friends with the 3D printer, can make it.

The device has measurements 76 * 61 * 22 mm.

You’ll find 3D models, PCB board, .hex and source code in the [repository](https://github.com/mangust01/MT.Strobic/tree/master/release).

## How it works?

An idea is based on serial flashing some or all 16 LEDs of a vertical led strip in curtain moment. Our inertial vision helps us to see a picture when the stroboscopic display is shaken but not the individual flashes. So, a camera need to be in high shutter mode to get the picture, cause high speed.

I use a simple vibration sensor to define a start position. Without this sensor we can not to display non-symmetric picture, for example words.

There are two shift registers on a PCB which control the 16 LEDs. A main controller is low voltage ATmega8A.

## Case parts

![MT.Strobic ABS version](/img/5.png)
<p align="center">Picture 2 - ABS version of the MT.Strobic (frontal side)</p>

![MT.Strobic ABS version](/img/6.png)
<p align="center">Picture 3 - ABS version of the MT.Strobic (back side)</p>

In the repository you can find 3D models of case parts. All in STL format. It can be manufactured by any 3D printer use both ABS or PLA polymers. The ABS version presented on pictures 2 and 3.

For smoother case surface, you should use an epoxy coating (for example, XTC-3D) or an acetone.

## Code

The source code is in the archive and a precompiled hex-file there too. So, you need any programmer for AVR8 MCUs to flash the hex-file in ATmega8A via SPI interface. There is a possibility to change the pictures (see the picture 4) via change matrixes in the source code. I use a chain of the CodeBlocks and the WinAVR for develop the source code and compilate it.
If you use new ATmega8A, you'll need to set the fuse bits. In the avrdude use following (with external 8MHz crystal):

    -U lfuse:w:0xfc:m -U hfuse:w:0xd9:m

![Pictures](/img/7.png)
<p align="center">Picture 4 - Pictures are displayed when the device is shaken</p>

## PCB

![PCB v2.0](/img/PCB.png)
<p align="center">Picture 5 - PCB v2.0</p>

The PCB designed in the Autodesk EAGLE Software for students (see the picture 5). An information about connections you’ll find in the EAGLE project. PCB is two layers board. It can be etched using Laser Printer at your home. Don’t forget to mirror a TOP layer before printing a template onto photo paper.

Table 1 - List of components

 №  |    Component                                            |    Qty.    |    Designation             
----|---------------------------------------------------------|------------|----------------------------
 1  |    Double-sided PCB   (FR4-2 56 * 48 mm)                |    1       |                            
 2  |    Steel axis   (Diameter * Length = 1 * 7 mm)          |    1       |                            
 3  |    PCB screw   (M2 * 6 or M2 * 8)                       |    4       |                            
 4  |    Housing parts screw   (M2 * 6, Head diameter = 3 mm) |    2       |                             
 5  |    ATMEGA8A-AU                                          |    1       |    IC1                     
 6  |    74HC595D                                             |    2       |    U1, U2                  
 7  |    LED   3528                                           |    16      |    LED1-LED16              
 8  |    CR2032 3V Coin Cell Battery Holder                   |    2       |    BT1,   BT2              
 9  |    MSK-12C02 SMD Switch                                 |    2       |    S1, S2                  
 10 |    HC49S crystal 8 MHz                                  |    1       |    Y1                      
 11 |    SMD 0603   12..22 pF ceramic capacitor               |    2       |    C1, C2                  
 12 |    SMD 0603   100 nF ceramic   capacitor                |    4       |    C5, C6,   C7, C8, C9    
 13 |    SMD 0402   100 nF ceramic   capacitor                |    2       |    C3, C4                  
 14 |    SMD   0603 4.7 k resistor                            |    2       |    R1, R2                  
 15 |    Pinhead   2.54 mm 2 * 3 pins                         |    1       |    JP2                     
 16 |    SW-520D vibration sensor (metal ball tilt switch)    |    1       |    JP1                     

## Controlling

Device starts working from switching on via a switch situated on the top side. A ‘NEXT’ button (right arrow) changes the displayed pictures. A ‘RESET’ button (curved arrow) returns to the first picture.

![Parts](/img/3.png)
<p align="center">Picture 6 - Parts</p>

## Battery power

The device uses the low voltage CR2032 battery (3V) as a power source. There are two parallel battery brackets in the device for a long using cycle. Changing discharged batteries is done by unscrewing the lids on backside (see the picture 7) with help of the coin for example.

![Battery lids](/img/4.png)
<p align="center">Picture 7 - Battery lids</p>
