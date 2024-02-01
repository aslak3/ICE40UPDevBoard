# ICE40UPDevBoard: an iCE40UP5K development board

![ICE40UPDevBoard PCB](/images/ICE40UPDevBoard.png)

## Features

The specification for this development board is as follows:

* [iCE40UP5K](https://www.latticesemi.com/view_document?document_id=51968) in QFN
* [N25Q032A](https://docs.rs-online.com/0866/0900766b80f7f8ab.pdf) 32 Mbit SPI flash
* DB15 VGA port:
  * [ADV7123](https://www.analog.com/media/en/technical-documentation/data-sheets/ADV7123-EP.pdf) RGB DAC
* PS/2 keyboard with two channels for a mouse and keyboard
* I2C:
  * [DS3231M](https://www.analog.com/media/en/technical-documentation/data-sheets/ds3231m.pdf) RTC
  * [AT24C64](https://ww1.microchip.com/downloads/en/devicedoc/doc0336.pdf) EEPROM
  * Header for I2C connections
* 3 LEDs and a button
* User header with 6 available FPGA pins
* Powered by a 5V switching regulator (eg a 5V [PM05S050A](https://filecenter.deltaww.com/products/download/01/0102/datasheet/DS_PM05S.pdf)) and a barrel jack

A [schematic](ICE40UPDevBoard.pdf) is included here, along with the
[KiCAD](https://www.kicad.org) data files, whcih are in  KiCAD 6 format.

## PCB design

The PCB is a 4 layer board.  My boards were manufactured by
[JLCPCB](https://www.jlcpcb.com).

## Using

The jumper mechanism to route the SPI signals which carry the configuration
data from the programmer was borrowed directly from the [Lattice’s iCE40
UltraPlus Breakout
Board](https://www.latticesemi.com/view_document?document_id=51987).

Any iCE40 compatible programmer should be useable.  I built my own, out of a
Pi Pico, which is documented in [another repo](https://github.com/aslak3/spi-flasher).
The programmer has been used to program both the attached flash and the FPGA directly.

## Possible gotchas

The design of this board is a very slightly tweaked version of the build I
have on my bench.  I have tweaked the LED and button connection after
finding out that the three LED pins on the iCE40UP cannot source current for
an LED and must sink it instead.

The following features have not been tested yet:

* I2C bus and peripheral ICs
* PS/2 port

## Blog

The best place to learn about this board is undoubtably [my
blog](https://www.aslak.net/), including this post:

* [Design and build of a Lattice iCE40UP development board](https://www.aslak.net/index.php/2024/01/31/design-and-build-of-a-lattice-ice40up-development-board/)
