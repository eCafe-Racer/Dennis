# Dennis

Dennis is a part of the eCafe Racer project, a collaboration between Tim
LaGreca, Jordyn Brosemer, and Connor Winiarczyk where we are attempting to
build an electric racing motorcycle for fun and street cred.

The board serve's as both a controller for the bike's 12V digital signals
(such as its turn signals and brake lights), and also as a general interface
to the bike's CAN bus. We plan to use this interface both during development
for things like data acquisition and validation testing, as well as in the 
final product in order to provide features like control over bluetooth and
diagnostics.


![Isometric View](https://raw.githubusercontent.com/eCafe-Racer/Dennis/master/Documentation/0.2.1/3D-renders/iso.jpg)


## Design 

Dennis was originally designed as a carrier board for the Raspberry Pi
[Compute Module 4](https://www.raspberrypi.org/products/compute-module-4/?variant=raspberry-pi-cm4001000),
which aimed to integrate a complete embedded Linux system with the rest of the
circuitry, with peripherals controlled directly by the Pi's GPIO pins.
There were a number of issues with this approach, not the least of which was
that, as hobbyists, we lacked the equipment required to reliably solder the
CM4's high density connectors. There were some more subtle issues as well,
including that the high level of integration made our design much more
difficult to modify, and that the need to include integrated communication
interfaces for the pi increased both the size of the board and its complexity.

Our solution was simply to remove the Compute Module from the design, replacing
it with an ESP32 microcontroller. The microcontroller will be able to perform 
some simple logical control over the board, but its main job will be to provide
an interface to the board's peripherals over UART or USB, allowing a more
powerful computer to connect and perform higher level control and more
sophisticated analysis.  

In order to make interfacing with external computers easier, a 12 pin connector
(J1) was added to Dennis that exactly matches the pinout of the first 12
pins of the 40 pin connector on a traditional Raspberry Pi board. This allows
a Raspberry Pi to be mounted adjacent to Dennis in whatever enclosure it is 
being used in, and with a single ribbon cable, connect to the ESP's UART
interface, as well as the strapping pins needed to do firmware updates, the
board's I2C bus, and 5V power supply. These signals can also be controlled
over USB by way of an MCP2221A, giving us the flexibility to use other external
computers as well.


## Peripherals

Dennis has a 12V GPIO system with 7 digital outputs and 4 digital inputs.
Digital outputs can be set to either 12V (on), or High Impedance (off), meaning
they cannot sink current. The digital inputs consist of two "signal" inputs,
which measure voltage, and two "switch" inputs, which measure resistance to
ground.
