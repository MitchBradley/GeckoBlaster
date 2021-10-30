## Gecko Blaster

Gecko Blaster is a small, inexpensive CNC controller board that is designed to
be used with FluidNC firmware https://github.com/bdring/FluidNC .  The microcontroller
is a an ESP32 in the D1 Mini form factor, like
https://www.aliexpress.com/item/1005001621844145.html or
https://www.amazon.com/ACEIRMC-ESP-WROOM-32-Bluetooth-Development-Compatible/dp/B08L5X2ZM3

The ESP32 Mini plugs into the Gecko Blaster board, and the board plugs
into a "standard" parallel port stepper driver, such as a Gecko G540 
https://www.geckodrive.com/g540-4-axis-digital-stepper-drive.html .
It should also work with a CNC breakout like
https://www.amazon.com/SainSmart-Breakout-Board-Stepper-Driver/dp/B0093Y897A
or a 3-axis (or 4-axis) driver board like
https://www.amazon.com/Stepper-Controller-Engraving-Milling-Machine/dp/B072J43CHP

Optionally, you can stack an OLED display shield like
https://www.amazon.com/Display-Module-SSD1306-ESP8266-Arduino/dp/B07P1QHTTK
on top of the ESP32 Mini to get some extra information from the firmware.

The Gecko Blaster board is very simple with only a few components other
than connectors, so it is very inexpensive to fabricate.  The components
are all through-hole for ease of soldering.

The board includes pads for a "Serial Wombat" I2C I/O Expander
https://www.amazon.com/Serial-Wombat-Converter-quadrature-Compatible/dp/B08T1QLSV8
attached to a rotary encoder with switch.  It was intended for controlling a
simple menu system for the OLED display.  The code for that has not been written.
That part of the hardware has not been tested; in fact the prototype PCB layout
had the pads for the Serial Wombat chip too far apart.  It would have been possible
to spread the pins and tack the chip down but I did not do so.

There are also pads for a pushbutton that connects to a GPIO.  It could be used
for some random control signal.  I do not use it at present.

The board is powered from a USB B connector that has only the power connections,
not the data lines.  I chose USB B because it is mechanically larger than
later USB connectors, and thus likely to be sturdier.  The power to the USB B
connector comes from an ordinary USB 5V wall cube.  There are no components that
require significant power, other than the ESP32, so an old-style 500mA USB
supply suffices.

The prototype, without the Serial Wombat and rotary switch, is in production
use on the CNC router that I use in my golf putter business.  The user interface
is a 10" Android tablet via the WebUI that is part of FluidNC.

The minimum system would need only three components besides the PCB:
1. The Mini ESP32 module (~$5)
2. A DB25 connector (~$1)
3. An electrolytic capacitor 100uF 25V (~$0.25)

[[/images/InUse.jpg|Gecko Blaster Installed on Geckodrive]
