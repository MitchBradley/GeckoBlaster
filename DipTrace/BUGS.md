## Bugs

# Version 1

- The footprint for the Serial Wombat chip is wrong - 400 mil spacing vs the correct 300 mils
- It needs an extra electrolytic capacitor from 5V to GND.  Otherwise the ESP32 Mini 5V tends to crash when the WiFi radio turns on.  On the prototype, I just tack-soldered a capacitor across the pins on the bottom of the board.  Anything 100 uF or larger is probably okay.
- I had to move one of the GPIOs.  ZDIR is on GPIO0, but when the board is plugged into a driver, the driver's optocoupler draws enough residual current to prevent the ESP32 from booting.  I reworked the board to move ZDIR over to GPIO14, which was the Aux switch.  The aux switch could be moved to GPIO0, but since I was not using it anyway I did not bother with that rework.
