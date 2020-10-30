# DFO_cdceprog_HEXfiles
This is a guide for programming DFOs for the Mega Drive, Playstation and Saturn with a Raspberry Pi. This corrects the sync frequence with a DFO (Dual Frequence Oscillator) to match 60Hz on PAL consoles. This is my collection of files to make the process much easier do. Credit goes to ikorb. 

To connect the DFO to the Raspberry Pi, check the nice overview of the
GPIO connector [here](http://pi.gadgetoid.com/pinout). The programming
pins on the side of the DFO must be connected as follows:

* DFO `SDA` to RasPi pin 3
* DFO `SCL` to RasPi pin 5
* DFO `GND` to RasPi pin 6
* DFO `3.3V` or `5V` to RasPi pin 1 or 2 (depends on the DFO board).

When connection is done, check if you can communicate with the clock generator chip on the DFO using:

       sudo i2cdetect -y 1

You should see a lot of dashes but in all those dashes there should be a number. If so, your good to go. If not, check your connections.












