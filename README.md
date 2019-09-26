
# C64 Joystick Switcher

I was watching [MsMadLemon](https://www.youtube.com/channel/UCSlMemxuBOFu6Rz_Al02nHQ) on [Youtube](https://youtu.be/DOF_CZoSF5g) the other day and she was making an autofire circuit, so naturally I wanted to build one too! Starting with the Mega Switcher for the Commodore 64 (switcher for using Sega Genisis/Mega Drive Controllers) I stripped away some parts to clear space for the autofire parts, and this project was the result of it all.

## Building the switcher
Soldering together the few components should be easy going as long as you have access to reasonable tools, personally I'm using a cheap soldering station with adjustable temperature so no need to go expensive if you don't have to. Use 60/40 soldering tin, the lead free makes to job a lot harder if you're new to the hobby.

Start by studying the PCB, both sides and perform dry fits to see that you have an idea of where everything goes since removing things is always a lot harder than getting it right in the first place (match orientation to symbols, see gallery images for reference if you're unsure). The diodes are installed standing, the stripe goes into the board so that it is laying directly against the board - a hint for making these look pretty, is wrapping one of the wires around a small screwdriver to get the loops looking almost identical!

The female DB9 connectors used for port 1/2 comes with a metal shroud, this comes off when you remove the two screws that would be in the way anyway. Given that the C64 ports are made out of plastic, the metal shroud is not needed though you could possibly keep it by gluing it to the connector if you really wanted to and then filling the screw holes with solder to keep them together afterwards. Do a testfit of the connectors with the C64 before soldering them to the board, this is recommended in order to avoid adding any stress to the C64 board.

![Components](https://github.com/tebl/C64-Mega-Switcher/raw/master/gallery/2019-07-30%2017.35.43.jpg)

## Using the switcher
Firmly insert the switcher into the C64, making sure that it is inserted the whole way and fits firmly without feeling loose. When playing a game, if you encounter a game that expects a joystick inserted into the other port you can use the switches to change the active port.

**WARNING!**
 - Do **NOT** move any of the jumpers while the computer is switched on, doing so may cause damage to it. Always power off first!
 - Do **NOT** jumper so that more than one button/direction does the same thing, for example: if you jumper the B1 button for UP, then you have to REMOVE the jumper enabling D-PAD UP!

# Schematic
The supplied KiCad files should be sufficient as both a schematic and as a  starting point for ordering PCBs (basically you could just zip the contents of the export folder and upload that on a fabrication site), the schematic is also available in [PDF-format](https://github.com/tebl/C64_Mega_Switcher/raw/master/export/C64%20Joystick%20Switcher.pdf) and this is what you'll need to print and work your way through this things don't work as expected after assembly.

# BOM
Most parts should be easy to get a hold of from your favourite local electronic component shop, but given that I don't have access to such shops where I live so everything was based on whatever I could get cheapest from ebay/AliExpress (free shipping, plan on usually waiting 3-4 weeks though).

| Reference    | Item                                  | Count |
| ------------ | ------------------------------------- | ----- |
| PCB          | Fabricate using Gerber files ([order](https://www.pcbway.com/project/shareproject/Commodore_64_Mega_Switcher.html?inviteid=88707))          |     1 |
| C1-C3        | 100nF capacitor                       |     3 |
| D1,D2        | 5mm LED                               |     2 |
| D3-D7        | 1N4148 diode                          |     5 |
| R1,R2        | 10k ohm resistor                      |     2 | 
| R3,R4        | 220 ohm resistor                      |     2 |
| U1           | 74HCT4053 or CD4053 DIP-16            |     2 |
| U3           | NE555 DIP-8                           |     1 |
| SW1,SW2      | SPST momentary push button            |     2 |
| JP1          | 2-pin straight header                 |     1 |
| J1,J2        | Female DB9 right-angle connector      |     2 |
| J3           | Male DB9 right-angle connector        |     1 |
| J4,J5        | 2x2-pin straight header               |     2 |