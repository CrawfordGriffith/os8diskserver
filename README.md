Multicomp PCB V0.1 (L. Ashmore '16)

This is the documentation for building the Printed Circuit Board (PCB) on dirtyPCBs.com site.  When I bought a set of these boards (12 of them),
there were no instructions on how to build it out, and I could not locate the creator of the board (L. Ashmore).  

This circuit board implements Grant Searle's Multicomp project.  You can read about Grant's project here:

Multicomp uses a Cyclone IV FPGA chip to emulate a number of classic microcomputer systems.  It does this by programming the FPGA to run the instuction
sets of those microcomputers.  The PCB expands the Cyclone miniboard with RAM, serial, VGA, keyboard interfaces.

The PCB, to a large extent follows what Grant did with point-to-point wiring.  Although relatively simple, the PCB avoids wiring errors (breaks, shorts, etc).

The Bill of Materials (BOM) is here.

Below are the build instructions.
0.  Orientation - for this build everything goes on the 'topside' of the card with the white lettering and outlines. Up will refer to the board pointed with the
	Serial, PS/2 and VGA connectors toward you, you can read MULTICPMP PCB V0.1 normally.


1.  Gather up the parts for the board.  Some of the parts are optional.  If you do not want to use a VGA output or PS/2 keyboard, leave them out, but then
	you will need to have the serial port (Max232)

2.  Start by soldering in the resistors.
	Resistors:  Red1, Green1, Blue1 - 680 Ohms
				Red2, Green2, Blue2 - 470 Ohms
				R11, R12 - 10K Ohms
				
3.  Next solder in the capacitors.
	Capacitors:	C1, C2 - 0.1 uF
				C6, C8, C9, c10 - 1uF electrolytics, observe polirity! For some reason, PCB's note the + (positive side), but capacitors usually mark - (minus side)
				C8 - 10uF electrolytic
				
4.  Solder in the Integrated Circuit (IC) sockets:
	IC Sockets:	16 Pin	- Best to align the socket notch the right way
				32 Pin - also chack the notch
				Note: the Sockets, and therefore the IC's point in different directions
				
5.  Now solder in the 28 pin headers (14 pins, 2 rows), there are 4 of them, as with sockets, it's best to solder 2 pins first, diagonally apart, whilst
	pressing on the header to make sure it is tight against the board.  When those pins are soldered and the header is tight to the board, solder the other pins.
	
6.  Solder in the VGA socket (if needed)

7.  Solder in the PS/2 keyboard socket and zener diodes and header (if needed)
	Diodes:	3.3V zeners - note the polarity of the diodes, the band on the diodes match the marking on the PCB
			3 pin header marked KEYVOLT with one jumper (left for 3v keyboard, right for 5V keyboard)
	Note:  The PCB can take either a 5V or 3.3V keyboard.  I was only able to determine the voltage by testing several to find a 3v one.  This is the easiest way
			If you only have 5V keyboards you will need to wire a cable from the Cyclone Miniboard 5V to the PCB 5V header.

8.  Solder in the female DB9 socket for serial (if needed)

9.  Solder in the other headers:
	Headers:	2 pin for 5VIN, as you look at the header reading 5VIN, + is right (or up with normal orientation) and - is left or down 
				7 pin male header for direct to SD card or
				7 pin female header for jumper wires to a SD card breakout
				
10.  SD Card installation.  There are a few options here.  You could solder a full size SD card or SD card to mini card adapter directly to the header pins.  This is fragile and 
	 Kind of ugly.  Or you can do what I did and use a SD card breakout board.  These boards have an SD card socket installed and pins that bring out the signals.
	 Unfortunatly, I have found no board that has the same pinout as the PCB, so you need to use wires to go from the header on the SD card breakout to the PCB header.
	 Jumper wires with male to female connectors work, or use a small perf board to do the trick.
	 SD header pinout, with the Serial, PS/2, Vga connectors pointed towards you left to right, suing SD card names for signals, with altenate names
		#1	DAT3/CS - also D3 - on the SD card, first retangular pin closest to the diagonal 'notch'  
		#2	CMD/DI 
		#3	Vss1 - Gnd 
		#4	Vcc  - 3.3 volts 
		#5	CLK
		#6	Vss2 - Gnd
		#7	DAT0/D0 - on the SD card this is the left side of the 'double-wide pin'
		
		
11.  Install the IC's.  Max232 chip points 'down', RAM chip pointe 'up'

12.  Install the cyclone minicard, UPSIDE DOWN, with the barrel jack to the right.  The Upside dowm minicard will protrude past the top of the main PCB.  This allows
	 the programming header cable to be attached when the miniboard is plugged in.
	 
	 
			
			
				
			