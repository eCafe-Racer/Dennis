# Dennis

Dennis is a part of the eCafe Racer project, a collaboration between Tim LaGreca, Jordyn Brosemer, and Connor Winiarczyk where we are attempting to build an electric racing motorcycle for fun and street cred. The board is an experimental computer with two purposes:

1. To operate our test equipment, providing an easy to use and compact interface between components on our test stand and human operators or management software.
2. A proof of concept for a low voltage management board that will be included in the final bike. The board will serve as an easy to program interface to the bike's CAN bus that will allow us to arbitrarily change the behavior of the other subsystems with certain CAN signals. It will also house a controller for the bike's brakes, turn signals, headlights, etc.

Dennis is a Carrier Board for Raspberry Pi's [Computer Module 4](https://www.raspberrypi.org/products/compute-module-4/?variant=raspberry-pi-cm4001000) which provides a set of peripherals and connectors specific to either of the purposes listed above. It is meant to be installed in one of two ways: In a test stand, where it can operate exactly like a traditional desktop computer, with dedicated connectors for a monitor, usb keyboard and mouse, wired internet, and DC power, or directly in the bike, where it will behave like a more standard embedded linux system, communicating primarily through CAN, or if possible, an internet connection.

Because Dennis is the first board we are developing for this project, and is at this time, explicitly experimental, we are trying to make it is as flexible as possible in order to accomodate the many possible uses we may find for it, hence the long list of peripherals, multiple installation modes, expansion slot, etc. It is likely that, as the project matures, we will gradually decide to reduce Dennis's scope.

![Isometric View](https://github.com/eCafe-Racer/Dennis/blob/master/Documentation/0.1.3/images/render_iso.jpg)

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
