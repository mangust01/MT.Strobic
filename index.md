## MT.Strobic

![MT.Strobic v2.0](/img/1.png)
<p align="center">Picture 1 - MT.Strobic</p>

MT.Strobic developed by me, when I studied on first semester of fourth year bachelor program at the Mechatronics Department (ITMO University, Saint-Petersburg, Russia).

MT.Strobic is just one more DIY stroboscopic display which you can find in the internet. It can be used just for fun or in more specific way. For example, as backpack flasher when you walk on unlit road in night time.

It’s not the easiest guide how to build this device, but I think, every high school schoolboy, who has electronics as a hobby and friends with the 3D printer, can make it.

The device has measurements 76 * 61 * 22 mm.

You’ll find 3D models, PCB board, list of components in the [repository](/release/).

## How it works?

An idea is based on serial flashing some or all 16 LEDs of a vertical led strip in curtain moment. Our inertial vision helps us to see a picture when the stroboscopic display is shaken but not the individual flashes. So, a camera need to be in high shutter mode to get the picture, cause high speed.

I use a simple vibration sensor to define a start position. Without this sensor we can not to display non-symmetric picture, for example words.

There are two shift registers on a PCB which control the 16 LEDs. A main controller is low voltage ATmega8A.

## Case parts

![MT.Strobic ABS version](/img/5.jpg)
<p align="center">Picture 2 - ABS version of the MT.Strobic (frontal side)</p>

![MT.Strobic ABS version](/img/6.jpg)
<p align="center">Picture 3 - ABS version of the MT.Strobic (back side)</p>

In the repository you can find 3D models of case parts. All in STL format. It can be manufactured by any 3D printer use both ABS or PLA polymers. The ABS version presented on pictures 2 and 3.

For smoother case surface, you should use an epoxy coating (for example, XTC-3D) or an acetone.

## Code

The source code is in the archive too and a precompiled hex-file there. So, you need any programmer for AVR8 MCUs to flash the hex-file in ATmega8A via SPI interface. There is a possibility to change the pictures (see the picture 4) via change matrixes in the source code. I use a chain of the CodeBlocks and the WinAVR for develop the source code and compilate it.

![Displayed pictures](/img/)
<p align="center">Picture 4 - Picture is displayed when the device is shaken</p>

## PCB

![PCB v2.0](/img/PCB.png)
<p align="center">Picture 5 - PCB v2.0</p>

The PCB designed in the Autodesk EAGLE Software for students (see the picture 5). An information about connections you’ll find in the EAGLE project. PCB is two layers board. It can be etched using Laser Printer at your home. Don’t forget to mirror a TOP layer before printing a template on photo paper.

## Controlling

Device starts working from switching on via a switch situated on the top side. A ‘NEXT’ button (right arrow) changes the displayed pictures. A ‘RESET’ button (curved arrow) returns to the first picture.

![Parts](/img/3.png)
<p align="center">Picture 6 - Parts</p>

## Battery power

The device uses the low voltage CR2032 battery (3V) as a power source. There are two parallel battery brackets in the device for a long using cycle. Changing discharged batteries is done by unscrewing the lids on backside (see the picture 5) with help of the coin for example.

![Battery lids](/img/4.png)
<p align="center">Picture 7 - Battery lids</p>
