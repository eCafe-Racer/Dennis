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


Dennis is a Carrier Board for Raspberry Pi's [Computer Module 4](https://www.raspberrypi.org/products/compute-module-4/?variant=raspberry-pi-cm4001000) which provides a set of peripherals and connectors specific to either of the purposes listed above. It is meant to be installed in one of two ways: In a test stand, where it can operate exactly like a traditional desktop computer, with dedicated connectors for a monitor, usb keyboard and mouse, wired internet, and DC power, or directly in the bike, where it will behave like a more standard embedded linux system, communicating primarily through CAN, or if possible, an internet connection.

Because Dennis is the first board we are developing for this project, and is at this time, explicitly experimental, we are trying to make it is as flexible as possible in order to accomodate the many possible uses we may find for it, hence the long list of peripherals, multiple installation modes, expansion slot, etc. It is likely that, as the project matures, we will gradually decide to reduce Dennis's scope.


A 3D render of Dennis from the top.

## Peripherals

- CAN interface
- 12V GPIO
- Ethernet
- HDMI
- 4x USB
- SD card reader
- Real Time Clock
- Ambient Temperature Sensor
- Expansion Slot
