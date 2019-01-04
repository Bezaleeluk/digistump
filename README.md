# digistump
This repository is a place where I can store for others use modified arduino IDE board definitions 
and other files for the Digistump Digispark Attiny boards.

Things done so far added Link Time Optimisation menu to the Digispark boards.
LTO seems to work and saves a few hundred bytes over standard builds.
Not all avr-gcc packages are built with the LTO module so you may get an error
if your build does not support it. Seek and ye shall find a better build!

Added a create disassembly recipe to the platform.txt to let us get an idea 
what's going on under the hood in assembly language.

Added option to burn fuses using an ISP and the burn bootloader option
current fuses do NOT disable the RST pin to gain a PB5 GPIO pin as that
complicates life if one wants to build using an ISP instead of micronucleus
bootloader. Since we by default run at 16.5MHz I set BOD to 4.3V not the default
2.7V which is probably too low a voltage to run the ATTINY85 at 16.5MHz clock.
