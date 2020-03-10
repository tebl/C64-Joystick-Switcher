# C64 Joystick Switcher
I was watching [MsMadLemon](https://www.youtube.com/channel/UCSlMemxuBOFu6Rz_Al02nHQ) on [Youtube](https://youtu.be/DOF_CZoSF5g) the other day and she was making an autofire circuit, so naturally I wanted to build one too! Starting with the [C64 Mega Switcher](https://github.com/tebl/C64-Mega-Switcher) for the Commodore 64 (when you want to use Sega Genesis or Mega Drive Controllers instead), I stripped away some parts to clear space for the autofire parts, redesigned it a couple of times and then finally sketched out the whole thing again in order to figure out all the ways it didn't work. The last one thankfully worked, so now it's open and available for anyone with fingers they are willing to risk burning with a soldering iron (don't do that by the way, it hurts)!

![C64 Joystick Switcher](https://github.com/tebl/C64-Joystick-Switcher/raw/master/gallery/2020-03-09%2021.38.28.jpg)

## Building the switcher
Soldering together the few components should be easy going as long as you have access to reasonable tools, personally I'm using a cheap soldering station with adjustable temperature so no need to go expensive if you don't have to. Use 60/40 soldering tin of reasonable quality, but stay away from the lead-free stuff unless you have experience working with it.

![Bare PCB](https://github.com/tebl/C64-Joystick-Switcher/raw/master/gallery/2020-03-09%2023.37.19.jpg)

Start by studying the PCB, both sides and perform dry fits to see that you have an idea of where everything goes since removing things is always a lot harder than getting it right in the first place (match orientation to symbols, see gallery images for reference if you're unsure). The diodes are installed standing, the stripe goes into the board so that it is laying directly against the board - a hint for making these look pretty, is wrapping one of the wires around a small screwdriver to get the loops looking almost identical!

![DB9 connector](https://github.com/tebl/C64-Joystick-Switcher/raw/master/gallery/2019-07-30%2017.35.43.jpg)

The female DB9 connectors used for port 1/2 comes with a metal shroud, this comes off when you remove the two screws that would be in the way anyway (see image above for reference). Given that the C64 ports are made out of plastic, the metal shroud is not needed though you could possibly keep it by gluing it to the connector if you really wanted to, alternatively you could also fill the mounting holes with solder to keep them together afterwards. Do a testfit of the connectors with the C64 before soldering them to the board, this is recommended in order to avoid adding any stress to the C64 board.

![Connected to C64](https://github.com/tebl/C64-Joystick-Switcher/raw/master/gallery/2020-03-09%2023.37.30.jpg)

Other than that, just take your time when doing the assembly - start by installing the smallest components first and then work your way up from there. Before actually plugging in anything into any antique computers, do a thorough visual inspection for any accidental solder-bridges. As a finishing note, I recommend putting something under the PCB to help support when pushing the buttons.

## Using the switcher
Firmly insert the switcher into the C64, making sure that it is inserted the whole way and fits firmly without feeling loose. When playing a game, if you encounter a game that expects a joystick inserted into the other port you can use the switches to change the currently active port.

**WARNING!**
 - Do **NOT** move any of the jumpers while the computer is switched on, doing so may cause damage to it. Always power off first!
 - Do **NOT** jumper so that more than one button/direction does the same thing, for example: if you jumper the B1 button for UP, then you have to REMOVE the jumper enabling D-PAD UP!
 - Do **NOT** use with actual Sega Genesis or Mega Drive controllers, if you want to use one of those - use [C64 Mega Switcher](https://github.com/tebl/C64-Mega-Switcher) instead.

You can use any common Atari-style joystick such as the Competition Pro and Zipstick, they are the ones I've tested with and currently also have in my collection. You can use the secondary fire button if you have one wired with this capability, most commonly the pinout is compatible with the Sega Master System gamepad. An auto-fire circuit has been added to the module, this can be handy if your controller does not include this functionality. 

# Schematic
The supplied KiCad files should be sufficient as both a schematic and as a  starting point for ordering PCBs (basically you could just zip the contents of the export folder and upload that on a fabrication site), the schematic is also available in [PDF-format](https://github.com/tebl/C64-Joystick-Switcher/raw/master/export/C64%20Joystick%20Switcher.pdf) and this is what you'll need to print and work your way through this things don't work as expected after assembly.

# BOM
Most parts should be easy to get a hold of from your favourite local electronic component shop, but given that I don't have access to such shops where I live so everything was based on whatever I could get cheapest from ebay/AliExpress (free shipping most places, but plan on waiting 3-4 weeks though). Pin headers are bought as strips with 40 pins, single or double rows, that you break into the specified sizes. Any amounts given in paranthesis are for optional functionality, mainly autofire and capability to utilize the secondary fire button if you have one. 

| Reference    | Item                                  | Count |
| ------------ | ------------------------------------- | ----- |
| PCB          | Fabricate using Gerber files ([order](https://www.pcbway.com/project/shareproject/Commodore_64_Joystick_Switcher__Revision_C_.html?inviteid=88707))          |     1 |
| C1-C4        | 100nF capacitor                       |     4 |
| C5           | 10uF electrolytic capacitor           |    (1)|
| D1,D2        | 5mm LED                               |     2 |
| J1,J2        | Female DB9 right-angle connector      |     2 |
| J3           | Male DB9 right-angle connector        |     1 |
| J4,J5        | 2x3-pin straight header               |     2 |
| JP2          | 3-pin straight header                 |     1 |
| Q1           | BC547 transistor (TO-92)              |    (1)|
| R1,R2        | 10k ohm resistor                      |     2 | 
| R3,R4        | 220 ohm resistor                      |     2 |
| R5,R7        | 2k2 (2200) ohm resistor               |    (2)|
| R6           | 100k ohm resistor                     |    (1)|
| R9           | 10k ohm resistor                      |    (1)| 
| RV1          | 10k ohm potentiometer (RM-065)        |    (1)| 
| U1,U2        | 74HCT4053 or CD4053 (DIP-16)          |     2 |
| U3           | NE555 (DIP-8)                         |     1 |
| U4           | NE555 (DIP-8)                         |    (1)|
| SW1,SW2      | SPST momentary push button            |     2 |