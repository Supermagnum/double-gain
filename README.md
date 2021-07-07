A small PCB that uses two NE5534 op amps to amplify a signal from a contact microphone.

It has balanced output,input and should run on +48 phantom power.
Shielded cable must be used for connection to the piezo crystals.
Please use metal film resistors with 1% tolerance or better and audio quality capacitors.
C0G (NP0) or X7R capacitors is very good.

It is important that the circuit board is mounted inside a metal box, and Ø2mm conducting metal standoffs are used.
The corner pads of the PCB board is reserved for that.
Of course the PCB board and components must not come in contact with any metal surface expect the standoffs.

The circuit may benefit from a Zobel network, that is a 680 pF capacitor and a 150 ohms resistor in series between pin 2 and 3 on the output connector. It should avoid high frequency oscillation in the cable.

Schematic diagram:
https://github.com/Supermagnum/double-gain/blob/main/double-gain.pdf

Component side picture with resistor values versus dB gain:
https://github.com/Supermagnum/double-gain/blob/main/components-side.jpg

Reverse side:
https://github.com/Supermagnum/double-gain/blob/main/back-side.jpg

PCB board dimensions:
https://github.com/Supermagnum/double-gain/blob/main/dimentions.png

Piezoelectric disk, red wire for positive polarity.
Black for negative: https://github.com/Supermagnum/double-gain/blob/main/Piezo-element-6.jpg

Aisler PCB boards:
https://aisler.net/p/GQFXIAWJ
They have all the parts too, it's included with the link.


Gerber files for PCB production:
https://github.com/Supermagnum/double-gain/tree/main/gerbers

PDF files for LASER etching ( these must be made negative, and holes drilled manually ):
https://github.com/Supermagnum/double-gain/tree/main/PDF-tracks

Ltspice simulation setup:
https://github.com/Supermagnum/double-gain/blob/main/Ltspice-setup.png

Ltspice frequency response:
https://github.com/Supermagnum/double-gain/blob/main/Frequency-response.png


+48 volt phantom power supply with mono headphone jack, runs on 9V battery:
https://github.com/Supermagnum/48power
It's only needed if you don't have a recorder that can provide 48 volts phantom power.
https://en.m.wikipedia.org/wiki/Phantom_power

They usually have a 3 pin XLR plug. Those are wired up like this: https://github.com/Supermagnum/piezo-balanced/blob/main/XLR%2BConnector%2BPinout%2BDiagram%2BRear%2BPin%2B2%2BHot%2Bv2%2Bgreen__01.jpg

NOTE:  
The XLR 3 pin plug has a solder lug for the shield for a reason.
It is my opinion that a shielded cable with 3 conductors inside is the best.
Suggested cable: Digi-Key Part Number: 30-00910-5-ND
	

Based on:
http://www.richardmudhar.com/blog/piezo-contact-microphone-hi-z-amplifier-low-noise-version/

It works nicely in LTspice, a program for simulation of circuits.

Why: The problem with piezo guitar pickups and piezoelectric crystals is that they are not well matched to typical audio inputs. By their nature they can generate a lot of signal, but they cannot drive a 50 kilohm typical line input. The pickup needs to work into a much higher impedance, typically 1 megohm or so.

So what to people do? They go and plug a piezoelectric disks output directly into the line input of their recorder, typical impedance 50k, or the plug-in-power mic input of their recorder, typical impedance about 7k, and they start to bitch and moan that this damn thing sounds tinny. Which is does ! But they don't understand why!

The reason why these devices often sound tinny is because the piezo sensor presents its signal through a series capacitance which is small, typically 15nF or less. When wired to a normal 50 kilohm line input this forms a high-pass filter, which eliminates the bass.

This circuit board solves that, and amplifies the signal. How many dB it amplifies is dependent on the resistance on the resistors used.The data for that is on the schematic diagram.

It's fairly easy and straight forward to solder the components to the circuit board, a nice pointy soldering iron, solder, a magnifying glass, and a ohm or multimeter is all that is needed. Of course one needs a suitable metal box, and the circuit boards components must not come in contact with the metal box. That will cause short circuit, so it's best mounted on stand offs. Also, use the magnifying glass to check that no one of the soldering pads has been bridged.

It can be used for a reverb plate, listening to the insides of a engine,recording the sound of vibrating things. You will need two piezoelectric disks for that, mounted in a metal box. Non electric conductive super glue is useable for that. Just glue them to a flat surface. The piezoelectric disks should be electrically insulated from the metal box.

Mechanics may even use it to discover trouble with bearings or other mechanisms not easily opened, but it will need a dedicated +48 volts phantom power supply with headphone jack for that specific usage.

Of course one can use a recorder like a tascam dr40x, as long as it can supply +48 volt phantom power, and has a headphone jack for monitoring.

A good set of headphones or ear protection with built in speakers will keep out unwanted sounds or noise.

Should also work nice with hydrophones. PZT-5H tubes is best for that. You want more gain, 35 or 40 dB for that. 
In case of a hydrophone it's possible to have the hydrophone attached with a long cable and the amplifier/buffer circuit close to the piezoelectric elements. 
It's of course extremely important that the circuit board and connections are absolutely waterproof. 
A epoxy filled container or inside the hydrophone bulb is OK. Commercial ones uses kerosene oil, so olive oil or sunflower oil is a great alternative as it will not pollute the environment if any leaks occurs.

Some interesting ideas can be found in: https://github.com/Supermagnum/piezo-balanced/blob/main/Barlow-et-al-2008-HydrophoneConstruction_TM-417.pdf Note: Ecopoxy Flowcast does not need any vacuum, just a mold and a way to hold the piezoelectric tubes centered. It's also safer to work with. Of course two piezoelectric disks inside something waterproof that can handle the water pressure is also useable.
Some methods of mounting a piezoelectric disk can be found here: https://locusonus.org/wiki/index.php?page=Hydrophone.en

Made with: http://www.kicad.org/

KiCad uses an integrated environment for all of the stages of the design process: Schematic capture, PCB layout, Gerber file generation/visualization, and library editing.

KiCad is a cross-platform program, and of curse free!


Built and works.

