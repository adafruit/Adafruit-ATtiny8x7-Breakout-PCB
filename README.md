## Adafruit ATtiny8x7 Breakout PCB

<a href="http://www.adafruit.com/products/5233"><img src="assets/5233.jpg?raw=true" width="500px"><br/>
Click here to purchase one from the Adafruit shop</a>

PCB files for the Adafruit ATtiny8x7 Breakout. 

Format is EagleCAD schematic and board layout
* https://www.adafruit.com/product/5233

### Description

This breakout board is a "three in one" product:

1. The ATtiny817 is part of the 'next gen' of AVR microcontrollers, and now we have a cute development/breakout board for it, with just enough hardware to get the chip up and running.
2. It's also an Adafruit seesaw board. Adafruit seesaw is a near-universal converter framework which allows you to add and extend hardware support to any I2C-capable microcontroller or microcomputer. Instead of getting separate I2C GPIO expanders, ADCs, PWM drivers, etc, seesaw can be configured to give a wide range of capabilities.
3. Finally, with STEMMA QT connectors on it, you could use it as either an I2C controller or peripheral with plug-and play support.

We primarily designed this board for our own use: it's a mini dev board that lets us design with the ATtiny817 just like we did for the ATSAMD09. With the 2021 silicon shortage, we're adapting some of our SAMD09 designs to the ATTiny8xx series and wanted a quick minimal board to test code on.

Each breakout comes with the assembled and tested board, as well as some header strips. Each PCB is fairly minimal and contains:

* ATtiny817 8-bit microcontroller
    * 8KB flash, 512 bytes of RAM, 128 bytes of EEPROM
    * Internal oscillator can run up to 20MHz
    * Internal hardware multiplier
    * Can run from 2V to 5V power/logic (check the datasheet for max speed at desired power)
* 3.3V regulator - by default we run at the Vin voltage, which can be 5V, but there's a solder jumper on the bottom if you'd like to select 3V logic.
* Green power LED
* Red indicator LED
* Two STEMMA QT I2C connectors with 10K pullup resistors, connected to pins 10 and 11

This board comes pre-programmed with seesaw peripheral code that will let it act as an "I2C to something" converter, basically a little I2C-controlled friend to do all the timing-sensitive things many microcontrollers and microcomputers are not good at.

For example, using this breakout with the pre-burned seesaw firmware gives you

* 14 x GPIO with selectable pullup resistors
* 9 x 10-bit ADC inputs - pins 0, 1, 2, 3, 6, 7, 18, 19, 20
* 5 x 8-bit PWM outputs - pins 0, 1, 9, 12, 13
* 1 x NeoPixel output (up to 60 pixels)
* 1 x EEPROM with 127 byte of NVM memory (handy for storing small access tokens or MAC addresses) - last byte of EEPROM is used for I2C address selection
* 1 x Interrupt output that can be triggered by any of the accessories - pin 15
* 2 x I2C address selection pins - pins 16 and 17
* 1 x Activity LED on pin 5, tied active low

Of course you can configure or reprogram the chip to however you want to use it - we like using SpenceKonde's megaTinyCore which brings Arduino peripheral support to this series of chips. To program the chip you will need a 'UPDI' programmer, which you can make with a USB-to-Serial cable and a single 4.7K or 10K resistor.

Please note: The boards do not come with a bootloader. If you want to do development on seesaw (e.g. changing the configuration) you need a separate UPDI programming setup! The firmware we put on is available as this example sketch, compiled using the megaTinyCore. We don't provide any support for custom builds of seesaw - we think this is cool and useful for the Maker community!

### License

Adafruit invests time and resources providing this open source design, please support Adafruit and open-source hardware by purchasing products from [Adafruit](https://www.adafruit.com)!

Designed by Limor Fried/Ladyada for Adafruit Industries.

Creative Commons Attribution/Share-Alike, all text above must be included in any redistribution. 
See license.txt for additional details.
