# Amiga_Ashcom_512Kb
Reproduction of the PCB for an Ashcom 512kb memory expansion, for Amiga 500s.   This was done as a learning exercise, after finding an Ashcom board with battery damage.  Rather than bodge the damaged board, I decided to replace the board.  Of course it would have been quicker and cheaper to buy a more modern equivalent, but where's the fun in that?

![3D Model](Amiga_Ashcom_512Kb_3d.png)

## Reproduction
The KiCad files (schematic and pcb) are available here.   Note the schematic and pcb were drawn separately.  I started with the intention of just re-creating the PCB, but then decided to create the schematic for completeness.  If there are any design issues with the expansion, then the issues will persist in this reproduction.  Along the same lines, neither I have replaced the battery with a CR2032.

## KiCAD Version 
KiCAD version 9.0.3

## Oddities
The dsign seems a somewhat more basic (and cheaper) design that the official A501 expansion.  Perhaps related to this, a few curiousousities were found:-
1) Pin 5 of the memory chips are documented as Not Connected.   Yet the PCB connects these pins to GND.
2) Pin 34 and Pin 33 on the connector are shorted.   Using Raemixx500 as a reference, these pins seem to be ~CLKCS and GND.  On an Amiga 501 the signal is sent to the RTC ~CS0 input, on the Ashcom it is grounded.  Another cost saving decision?
3) The RTC clock circuit has only fix capacitors (the A501 has a fixed and variable capacitor with the crystal).
4) The holes for C9 are present on the original PCB, but not populated.  As there are no component markings, Ive assumed this was intended for a capacitor across VDD and GND (on the RTC IC), but the manufacturer obviously didnt feel this capacitor was necessary
5) There are no decoupling capacitors across VCC and GND for U2 and U6.  Either the manufacturer didn't think decoupling capacitors were needed for U2 and U5, or it's another cost saving decision.

In summary this seems a stripped down design when compared to the A501.  Does this have any nagative implications?

## Gerbers and PCB Production
I have not yet printed any PCBs, so this project is currently for documentation purposes only.  Gerber files are included but note these are experimental (ie untested).

## References
1) https://github.com/SukkoPera/Raemixx500 
2) https://amigawiki.org/dnl/schematics/A500_R6.pdf

## Damaged PCB Pictures
The following pictures show the original PCBs, and were used to recreate the PCB layout.
<img src="pcb_front_straightened.jpg" alt="PCB Front Image" width="50%" height="50%">
<img src="pcb_back_straightened.jpg" alt="PCB Front Image" width="50%" height="50%">



