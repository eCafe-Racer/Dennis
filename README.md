# Dennis

Dennis is a part of the eCafe Racer project, a collaboration between Tim LaGreca, Jordyn Brosemer, and Connor Winiarczyk where we are attempting to build an electric racing motorcycle for fun and street cred. The board is an experimental computer with two purposes:

1. To operate our test equipment, providing an easy to use and compact interface between components on our test stand and human operators or management software.
2. A proof of concept for a low voltage management board that will be included in the final bike. The board will serve as an easy to program interface to the bike's CAN bus that will allow us to arbitrarily change the behavior of the other subsystems with certain CAN signals. It will also house a controller for the bike's brakes, turn signals, headlights, etc.

It is a carrier board for the Raspberry Pi Compute Module 4 with a compact form factor and peripherals specific to its automotive application.

# Peripherals

- CAN interface
- Ethernet
- SD card reader
- 12V GPIO
- Real Time Clock
